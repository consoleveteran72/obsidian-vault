
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
