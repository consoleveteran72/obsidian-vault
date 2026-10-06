```rust
use std::fs;
use std::io;
use std::thread;
use std::time::Duration;

const HWMON_PATH: &str = "/sys/class/hwmon";
const BATTERY_PATH: &str = "/sys/class/power_supply/BAT0";
const PROFILE_PATH: &str = "/sys/firmware/acpi/platform_profile";

/// Read a text file from sysfs and remove the trailing newline.
fn read_file(path: &str) -> Option<String> {
    fs::read_to_string(path)
        .ok()
        .map(|value| value.trim().to_string())
}

/// Read a sysfs value as a floating-point number.
fn read_number(path: &str) -> Option<f64> {
    read_file(path)?.parse::<f64>().ok()
}

/// Find the hwmon directory belonging to a particular driver name.
///
/// For example:
/// "k10temp" -> /sys/class/hwmon/hwmon9
/// "amdgpu"  -> /sys/class/hwmon/hwmon8
fn find_hwmon(name: &str) -> Option<String> {
    let entries = fs::read_dir(HWMON_PATH).ok()?;

    for entry in entries.flatten() {
        let path = entry.path();

        let name_path = path.join("name");

        if let Ok(hwmon_name) = fs::read_to_string(name_path) {
            if hwmon_name.trim() == name {
                return Some(path.to_string_lossy().into_owned());
            }
        }
    }

    None
}

/// Read a temperature from a hwmon sensor.
///
/// Linux hwmon normally reports temperatures in millidegrees Celsius.
///
/// Example:
/// 37500 -> 37.5 °C
fn read_temperature(hwmon: &str, file: &str) -> Option<f64> {
    let path = format!("{}/{}", hwmon, file);

    read_number(&path).map(|value| value / 1000.0)
}

/// Read fan RPM from the ASUS hwmon driver.
fn read_fan_rpm(hwmon: &str, file: &str) -> Option<u64> {
    let path = format!("{}/{}", hwmon, file);

    read_number(&path).map(|value| value as u64)
}

/// Read the battery percentage.
fn read_battery() -> Option<u64> {
    let path = format!("{}/capacity", BATTERY_PATH);

    read_number(&path).map(|value| value as u64)
}

/// Read the current ASUS platform profile.
fn read_profile() -> Option<String> {
    read_file(PROFILE_PATH)
}

/// Find all hwmon devices using the "nvme" driver.
fn find_nvme_hwmons() -> Vec<String> {
    let mut devices = Vec::new();

    let entries = match fs::read_dir(HWMON_PATH) {
        Ok(entries) => entries,
        Err(_) => return devices,
    };

    for entry in entries.flatten() {
        let path = entry.path();
        let name_path = path.join("name");

        if let Ok(name) = fs::read_to_string(name_path) {
            if name.trim() == "nvme" {
                devices.push(path.to_string_lossy().into_owned());
            }
        }
    }

    devices.sort();

    devices
}

/// Clear the terminal screen and move the cursor to the top-left corner.
fn clear_screen() {
    print!("\x1B[2J\x1B[1;1H");
}

/// Print one dashboard update.
fn print_dashboard() {
    let cpu_hwmon = find_hwmon("k10temp");
    let gpu_hwmon = find_hwmon("amdgpu");
    let asus_hwmon = find_hwmon("asus");

    let cpu_temp = cpu_hwmon
        .as_deref()
        .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));

    let gpu_temp = gpu_hwmon
        .as_deref()
        .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));

    let gpu_power = gpu_hwmon
        .as_deref()
        .and_then(|hwmon| read_number(&format!("{}/power1_input", hwmon)))
        .map(|value| value / 1_000_000.0);

    let cpu_fan = asus_hwmon
        .as_deref()
        .and_then(|hwmon| read_fan_rpm(hwmon, "fan1_input"));

    let gpu_fan = asus_hwmon
        .as_deref()
        .and_then(|hwmon| read_fan_rpm(hwmon, "fan2_input"));

    let battery = read_battery();

    let profile = read_profile()
        .unwrap_or_else(|| "unknown".to_string());

    let nvme_devices = find_nvme_hwmons();

    let ssd1_temp = nvme_devices
        .get(0)
        .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));

    let ssd2_temp = nvme_devices
        .get(1)
        .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));

    clear_screen();

    println!("╔════════════════════════════════════════╗");
    println!("║        ASUS TUF GAMING A16             ║");
    println!("║             FA617NS                    ║");
    println!("╠════════════════════════════════════════╣");

    print_value("CPU", cpu_temp, "°C", 7);
    print_value("GPU", gpu_temp, "°C", 7);

    print_integer_value("CPU Fan", cpu_fan, " RPM");
    print_integer_value("GPU Fan", gpu_fan, " RPM");

    print_value("GPU Power", gpu_power, " W", 7);

    print_value("SSD 1", ssd1_temp, "°C", 7);
    print_value("SSD 2", ssd2_temp, "°C", 7);

    match battery {
        Some(value) => println!("║ {:<18} {:>16}% ║", "Battery", value),
        None => println!("║ {:<18} {:>16}  ║", "Battery", "N/A"),
    }

    println!("╠════════════════════════════════════════╣");
    println!("║ {:<18} {:>16}   ║", "Profile", profile);
    println!("╚════════════════════════════════════════╝");
}

/// Print a floating-point value such as temperature or power.
fn print_value(
    label: &str,
    value: Option<f64>,
    unit: &str,
    _width: usize,
) {
    match value {
        Some(value) => {
            println!(
                "║ {:<18} {:>13.1}{} ║",
                label,
                value,
                unit
            );
        }

        None => {
            println!(
                "║ {:<18} {:>16} ║",
                label,
                "N/A"
            );
        }
    }
}

/// Print an integer value such as fan RPM.
fn print_integer_value(
    label: &str,
    value: Option<u64>,
    unit: &str,
) {
    match value {
        Some(value) => {
            println!(
                "║ {:<18} {:>13}{} ║",
                label,
                value,
                unit
            );
        }

        None => {
            println!(
                "║ {:<18} {:>16} ║",
                label,
                "N/A"
            );
        }
    }
}

fn main() {
    loop {
        print_dashboard();

        thread::sleep(Duration::from_secs(1));
    }
}
```

### How to compile

Create a Rust project:

```bash
cargo new tuf-control-center
cd tuf-control-center
```

Replace `src/main.rs` with the code above, then:

```bash
cargo run
```

You should get a dashboard that refreshes every second.

---

## Line-by-line explanation

### 1. Imports

```rust
use std::fs;
```

Imports Rust's filesystem module.

We need this because Linux exposes your hardware information as files under `/sys`.

For example:

```text
/sys/class/hwmon/hwmon9/temp1_input
```

is a file that contains the CPU temperature.

---

```rust
use std::io;
```

This imports Rust's standard input/output module.

**In this version it isn't actually needed**, so it can be removed. I left it here only if you later want keyboard controls such as `q` to quit or `p` to change profile.

A cleaner version would therefore omit it.

---

```rust
use std::thread;
```

Imports Rust's thread functionality.

We use it to pause the program between dashboard updates.

---

```rust
use std::time::Duration;
```

Imports `Duration`, which lets us specify time intervals.

We eventually use:

```rust
Duration::from_secs(1)
```

meaning **one second**.

---

## 2. Linux paths

```rust
const HWMON_PATH: &str = "/sys/class/hwmon";
```

Creates a constant containing the location of Linux's hardware-monitoring interfaces.

Your machine has directories such as:

```text
/sys/class/hwmon/hwmon3
/sys/class/hwmon/hwmon8
/sys/class/hwmon/hwmon9
```

---

```rust
const BATTERY_PATH: &str = "/sys/class/power_supply/BAT0";
```

This points to your laptop battery.

For example:

```text
/sys/class/power_supply/BAT0/capacity
```

contains the battery percentage.

---

```rust
const PROFILE_PATH: &str = "/sys/firmware/acpi/platform_profile";
```

This points to your ASUS performance profile.

On your machine it contains values such as:

```text
quiet
balanced
performance
```

---

# 3. Reading files

```rust
fn read_file(path: &str) -> Option<String> {
```

Defines a function called `read_file`.

It accepts a filesystem path.

For example:

```text
/sys/class/hwmon/hwmon9/temp1_input
```

The return type is:

```rust
Option<String>
```

Rust's `Option` means:

- `Some(value)` → successfully read
    
- `None` → couldn't read it
    

This is useful because hardware interfaces can disappear or fail.

---

```rust
fs::read_to_string(path)
```

Reads the entire file as text.

For example, if the file contains:

```text
37500
```

Rust receives the string:

```text
"37500\n"
```

---

```rust
.ok()
```

Converts a filesystem error into `None`.

Instead of crashing if something goes wrong, we get:

```rust
None
```

---

```rust
.map(|value| value.trim().to_string())
```

Removes whitespace and the newline.

So:

```text
"37500\n"
```

becomes:

```text
"37500"
```

---

```rust
}
```

Ends the function.

---

# 4. Reading numbers

```rust
fn read_number(path: &str) -> Option<f64> {
```

This function reads a sysfs file and converts its contents into a floating-point number.

For example:

```text
37500
```

becomes:

```text
37500.0
```

---

```rust
read_file(path)?
```

Calls our previous function.

The `?` operator means:

> If reading failed, immediately return `None`.

---

```rust
.parse::<f64>().ok()
```

Converts the text into an `f64`.

`f64` is Rust's 64-bit floating-point type.

---

# 5. Finding a hardware device

```rust
fn find_hwmon(name: &str) -> Option<String> {
```

This is an important function.

We **don't want to hard-code**:

```text
hwmon9 = CPU
hwmon8 = GPU
```

because those numbers can change between boots.

Instead we look at:

```text
/sys/class/hwmon/hwmon9/name
```

which contains:

```text
k10temp
```

---

```rust
let entries = fs::read_dir(HWMON_PATH).ok()?;
```

Gets all directories inside:

```text
/sys/class/hwmon
```

For your machine, these include:

```text
hwmon0
hwmon1
hwmon2
...
hwmon12
```

---

```rust
for entry in entries.flatten() {
```

Loops through those directories.

---

```rust
let path = entry.path();
```

Gets the current directory path.

For example:

```text
/sys/class/hwmon/hwmon9
```

---

```rust
let name_path = path.join("name");
```

Creates:

```text
/sys/class/hwmon/hwmon9/name
```

---

```rust
if let Ok(hwmon_name) = fs::read_to_string(name_path) {
```

Reads the `name` file.

---

```rust
if hwmon_name.trim() == name {
```

Checks whether it matches what we're looking for.

For example:

```rust
find_hwmon("k10temp")
```

will search for:

```text
name = k10temp
```

---

```rust
return Some(path.to_string_lossy().into_owned());
```

If found, return its path.

For example:

```text
/sys/class/hwmon/hwmon9
```

---

```rust
None
```

If nothing matched, return `None`.

---

# 6. Temperature

```rust
fn read_temperature(hwmon: &str, file: &str) -> Option<f64> {
```

Reads a temperature from an hwmon device.

---

```rust
let path = format!("{}/{}", hwmon, file);
```

Combines two strings.

For example:

```text
/sys/class/hwmon/hwmon9
```

and:

```text
temp1_input
```

become:

```text
/sys/class/hwmon/hwmon9/temp1_input
```

---

```rust
read_number(&path).map(|value| value / 1000.0)
```

This is important.

Linux reports your CPU temperature as:

```text
37500
```

which means:

```text
37.5 °C
```

Therefore we divide by 1000.

---

# 7. Fan speed

```rust
fn read_fan_rpm(hwmon: &str, file: &str) -> Option<u64> {
```

Reads fan speed.

Your ASUS hwmon interface provides:

```text
fan1_input
fan2_input
```

with values such as:

```text
1800
```

meaning:

```text
1800 RPM
```

---

```rust
.map(|value| value as u64)
```

Converts the number to an integer.

---

# 8. Battery

```rust
fn read_battery() -> Option<u64> {
```

Defines a battery-reading function.

---

```rust
let path = format!("{}/capacity", BATTERY_PATH);
```

Creates:

```text
/sys/class/power_supply/BAT0/capacity
```

---

```rust
read_number(&path).map(|value| value as u64)
```

Reads the percentage.

For example:

```text
87
```

becomes:

```text
87%
```

---

# 9. Performance profile

```rust
fn read_profile() -> Option<String> {
```

Defines the profile-reading function.

---

```rust
read_file(PROFILE_PATH)
```

Reads:

```text
/sys/firmware/acpi/platform_profile
```

which could return:

```text
quiet
```

or:

```text
balanced
```

or:

```text
performance
```

---

# 10. Finding SSD sensors

```rust
fn find_nvme_hwmons() -> Vec<String> {
```

Returns a vector containing every hwmon device whose name is:

```text
nvme
```

Your system currently has two:

```text
hwmon5
hwmon6
```

---

```rust
let mut devices = Vec::new();
```

Creates an empty list.

---

```rust
let entries = match fs::read_dir(HWMON_PATH) {
```

Attempts to read `/sys/class/hwmon`.

---

```rust
Ok(entries) => entries,
```

If successful, continue.

---

```rust
Err(_) => return devices,
```

If it fails, return an empty list.

---

```rust
for entry in entries.flatten() {
```

Loop through all hwmon devices.

---

```rust
if name.trim() == "nvme" {
```

Check whether the device is an NVMe sensor.

---

```rust
devices.push(path.to_string_lossy().into_owned());
```

Add the device to our list.

---

```rust
devices.sort();
```

Sort the list so that its order is deterministic.

---

# 11. Clearing the terminal

```rust
fn clear_screen() {
```

Defines the screen-clearing function.

---

```rust
print!("\x1B[2J\x1B[1;1H");
```

These are ANSI terminal escape sequences.

The first part:

```text
\x1B[2J
```

clears the screen.

The second:

```text
\x1B[1;1H
```

moves the cursor to the top-left.

So instead of printing hundreds of lines:

```text
CPU: 37
CPU: 37
CPU: 38
CPU: 38
...
```

we overwrite the same dashboard.

---

# 12. Main dashboard function

```rust
fn print_dashboard() {
```

This function collects all hardware information and prints the dashboard.

---

```rust
let cpu_hwmon = find_hwmon("k10temp");
```

Searches for your AMD CPU temperature driver.

On your system:

```text
k10temp -> hwmon9
```

---

```rust
let gpu_hwmon = find_hwmon("amdgpu");
```

Finds the AMD GPU sensor.

On your system:

```text
amdgpu -> hwmon8
```

---

```rust
let asus_hwmon = find_hwmon("asus");
```

Finds the ASUS driver.

On your system:

```text
asus -> hwmon3
```

This is where your fan RPM values come from.

---

# 13. CPU temperature

```rust
let cpu_temp = cpu_hwmon
    .as_deref()
    .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));
```

This looks complicated, but conceptually it says:

> If we found the `k10temp` device, read its `temp1_input`.

Your actual path is:

```text
/sys/class/hwmon/hwmon9/temp1_input
```

and its value is approximately:

```text
37500
```

which becomes:

```text
37.5
```

---

# 14. GPU temperature

```rust
let gpu_temp = gpu_hwmon
    .as_deref()
    .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));
```

Same idea.

Your GPU sensor:

```text
/sys/class/hwmon/hwmon8/temp1_input
```

currently reports approximately:

```text
37000
```

so the dashboard displays:

```text
37.0 °C
```

---

# 15. GPU power

```rust
let gpu_power = gpu_hwmon
    .as_deref()
    .and_then(|hwmon| read_number(&format!("{}/power1_input", hwmon)))
    .map(|value| value / 1_000_000.0);
```

Your AMD GPU exposes:

```text
power1_input
```

Your current value was:

```text
6000000
```

Linux reports this in **microwatts**.

Therefore:

```text
6,000,000 µW
----------------
1,000,000

= 6 W
```

The dashboard therefore shows:

```text
GPU Power  6.0 W
```

---

# 16. CPU fan

```rust
let cpu_fan = asus_hwmon
    .as_deref()
    .and_then(|hwmon| read_fan_rpm(hwmon, "fan1_input"));
```

Your ASUS hwmon device has:

```text
fan1_label = cpu_fan
fan1_input = 1800
```

So this displays:

```text
CPU Fan 1800 RPM
```

---

# 17. GPU fan

```rust
let gpu_fan = asus_hwmon
    .as_deref()
    .and_then(|hwmon| read_fan_rpm(hwmon, "fan2_input"));
```

Your system reports:

```text
fan2_label = gpu_fan
fan2_input = 1800
```

So:

```text
GPU Fan 1800 RPM
```

---

# 18. Battery

```rust
let battery = read_battery();
```

Reads:

```text
/sys/class/power_supply/BAT0/capacity
```

---

# 19. Profile

```rust
let profile = read_profile()
    .unwrap_or_else(|| "unknown".to_string());
```

Reads your current profile.

If the file cannot be read, it displays:

```text
unknown
```

instead of crashing.

---

# 20. NVMe drives

```rust
let nvme_devices = find_nvme_hwmons();
```

Gets all NVMe temperature sensors.

For your system this currently finds two.

---

```rust
let ssd1_temp = nvme_devices
    .get(0)
    .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));
```

Gets the first NVMe device.

---

```rust
let ssd2_temp = nvme_devices
    .get(1)
    .and_then(|hwmon| read_temperature(hwmon, "temp1_input"));
```

Gets the second.

One important detail: **these are currently "NVMe sensor 1" and "NVMe sensor 2", not guaranteed physical SSD 1 and SSD 2.**

To make the dashboard correctly say something like:

```text
Samsung 980 PRO
WD SN770
```

we would need to associate each hwmon device with its actual `/dev/nvmeX` device.

---

# 21. Drawing the dashboard

```rust
clear_screen();
```

Clears the previous dashboard.

---

```rust
println!("╔════════════════════════════════════════╗");
```

Prints the top border.

`println!` means:

> Print this text and then move to the next line.

---

```rust
println!("║        ASUS TUF GAMING A16             ║");
```

Prints your laptop name.

---

```rust
println!("║             FA617NS                    ║");
```

Prints your model.

---

```rust
println!("╠════════════════════════════════════════╣");
```

Prints the separator.

---

# 22. Printing values

```rust
print_value("CPU", cpu_temp, "°C", 7);
```

Prints the CPU temperature.

For example:

```text
CPU              37.5°C
```

---

```rust
print_value("GPU", gpu_temp, "°C", 7);
```

Prints GPU temperature.

---

```rust
print_integer_value("CPU Fan", cpu_fan, " RPM");
```

Prints CPU fan RPM.

---

```rust
print_integer_value("GPU Fan", gpu_fan, " RPM");
```

Prints GPU fan RPM.

---

```rust
print_value("GPU Power", gpu_power, " W", 7);
```

Prints GPU power.

---

```rust
print_value("SSD 1", ssd1_temp, "°C", 7);
```

Prints the first NVMe temperature.

---

```rust
print_value("SSD 2", ssd2_temp, "°C", 7);
```

Prints the second.

---

# 23. Battery match

```rust
match battery {
```

Rust's `match` lets us handle both possibilities.

---

```rust
Some(value) => ...
```

Means:

> We successfully got a battery value.

---

```rust
None => ...
```

Means:

> We couldn't read the battery.

Instead of crashing, we display:

```text
Battery             N/A
```

---

# 24. Profile

```rust
println!("║ {:<18} {:>16}   ║", "Profile", profile);
```

Prints something like:

```text
Profile                 quiet
```

The formatting:

```text
{:<18}
```

means left-align the text in 18 spaces.

And:

```text
{:>16}
```

means right-align it in 16 spaces.

---

# 25. `print_value`

```rust
fn print_value(
    label: &str,
    value: Option<f64>,
    unit: &str,
    _width: usize,
)
```

This function prints values such as:

```text
37.5 °C
6.0 W
```

The `_width` parameter is currently unused.

The underscore tells Rust:

> I intentionally don't use this variable.

Actually, we can simplify this function further by removing `_width` entirely. It was inherited from the earlier Python layout idea.

---

```rust
match value {
```

Again, we check whether we have a value.

---

```rust
Some(value) => {
```

If we have one, print it.

---

```rust
println!(
    "║ {:<18} {:>13.1}{} ║",
    label,
    value,
    unit
);
```

The `.1` means:

> Display one digit after the decimal point.

Therefore:

```text
37.5
```

instead of:

```text
37.500000
```

---

```rust
None => {
```

If the sensor isn't available:

```text
N/A
```

is printed.

---

# 26. `print_integer_value`

This is almost identical, except it is intended for integer values such as:

```text
1800 RPM
```

rather than:

```text
37.5 °C
```

---

# 27. `main`

```rust
fn main() {
```

This is where every Rust program starts.

---

```rust
loop {
```

Creates an infinite loop.

Conceptually:

```text
while true:
    update dashboard
    wait
```

---

```rust
print_dashboard();
```

Collects all the sensor values and prints the dashboard.

---

```rust
thread::sleep(Duration::from_secs(1));
```

Waits one second.

Then the loop starts again.

So the program does:

```text
┌─────────────────┐
│ Read sensors    │
│       ↓         │
│ Print dashboard │
│       ↓         │
│ Wait 1 second   │
│       ↓         │
│ Read sensors    │
│       ↓         │
│      ...        │
└─────────────────┘
```

### One small cleanup

The code above contains:

```rust
use std::io;
```

but doesn't use it. You can safely delete that line.

Also, the `_width` parameter in `print_value()` isn't necessary. The cleaner production version would remove both.