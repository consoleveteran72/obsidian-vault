

To restart:
```bash
sudo systemctl restart asusd
``` 

To turn on fan_curves:
```bash
sudo asusctl fan-curve --enable-fan-curves true --mod-profile quiet
```

To check if fan_curves are turned on:
```bash
sensors | grep -A3 -B2 'asus_custom'
```
