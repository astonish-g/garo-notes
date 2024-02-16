---
dg-publish: true
---
##### Problem:
When you connect your mouse or keyboard or whatever in bluetooth to your computer, it may have issues that it goes to sleep every few seconds and after a few seconds of inactivity and it may take a second till it wakes up again. Obviously it is very annoying when you use your mouse or keyboard this way.

##### How to fix it?
Execute the solution below step by step.
###### Find vendor and product ID:
Find vendor and product ID of your Bluetooth chip/dongle with these two commands:

```bash
cat `readlink -f /sys/class/bluetooth/hci0`/../../../idVendor
cat `readlink -f /sys/class/bluetooth/hci0`/../../../idProduct
```

In my case, **vendor ID = 0489** and **product ID = e0cd** 

###### Create a USB power save rule:
In the example below, we will fine tune the delayt time per device by setting the `power/autosuspend` attribute. This means, alternatively, autosuspend can be disabled by setting `power/autosuspend` to **-1** which means to **never autosuspend**.

To do this, create and add this udev rule `/etc/udev/rules.d/50-usb_power_save.rules` with the attributes below. Let's consider that our **vendor ID** is **0489** and **product ID** is **e0cd**:

```bash
ACTION=="add", SUBSYSTEM=="usb", ATTR{idVendor}=="0489", ATTR{idProduct}=="e0cd", ATTR{power/autosuspend}="-1"
```

After you save the `udev rule` above, ==reload udev rules== with these commands:

```bash
sudo udevadm control --reload
sudo udevadm trigger
```

You **may** also **need to restart bluetooth** wth the following command:

```bash
systemctl restart bluetooth
```

In ==alternatively== you can ==restart== your computer.

> [!tip]- Useful links
> [Linux Mint Forum explanation](https://forums.linuxmint.com/viewtopic.php?t=271531)
> [Arch Wiki USB autosuspend](https://wiki.archlinux.org/title/Power_management#USB_autosuspend)