
keyboard lights:

directory:

```bash
echo 2 | sudo tee /sys/class/leds/asus::kbd_backlight/brightness
```

Hardware can be controlled through the sys directory.

https://wiki.archlinux.org/title/Laptop/ASUS

battery charge threshold
```bash
cat /sys/class/power_supply/BAT0/status #charging/discharging

cat /sys/class/power_supply/BAT0/capacity

echo 60 > /sys/class/power_supply/BAT0/charge_control_end_threshold
#set charge limit to 60
```


# important

/sys/class/firmware-attributes/asus-armoury

/sys/class/platform-profile

/sys/class/thermal/thermal_zone0

/sys/class/wmi_bus

/sys/class/pci_bus

/sys/class/ `drm` / `graphics` / `kfd` / `accel`

/sys/class/hwmon/hwmon1 - thermal
/sys/class/hwmon/hwmon3 - cpu_fan
/sys/class/hwmon/hwmon4 - asus_custom_fan_curve
/sys/class/hwmon/hwmon8 - amdgpu

/sys/class/backlight
/sys/class/leds
