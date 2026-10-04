
keyboard lights:

directory:

/sys/class/leds/asus::kbd_backlight/brightness

```bash
echo 2 | sudo tee /sys/class/leds/asus::kbd_backlight/brightness
```

Hardware can be controlled through the sys directory.

https://wiki.archlinux.org/title/Laptop/ASUS