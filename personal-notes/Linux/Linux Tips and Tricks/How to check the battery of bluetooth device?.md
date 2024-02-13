---
dg-publish: true
---
##### The less sophisticated way:
- In your terminal execute the `upower --dump` command.
- It will produce a long output. In that output, find your bluetooth device, and check the value next to the `percentag`
##### Here's an example output:
```bash
Device: /org/freedesktop/UPower/devices/keyboard_dev_E9_05_14_DB_C8_26
  native-path:          /org/bluez/hci0/dev_E9_05_14_DB_C8_26
  model:                NuPhy Air60 V2-1
  serial:               E9:05:14:DB:C8:26
  power supply:         no
  updated:              gio 8 feb 2024, 23:20:58 (314 seconds ago)
  has history:          yes
  has statistics:       no
  keyboard
    present:             yes
    rechargeable:        no
    state:               unknown
    warning-level:       none
    percentage:          79%
    icon-name:          'battery-missing-symbolic'
```
And in the example above, you can see that my Nuphy keyboard's battery level is 79%.