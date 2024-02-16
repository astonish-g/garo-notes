---
dg-publish: true
---
In order for your keyboard to be detected by the VIA and Vial apps on Linux, you need to set up a custom `udev` rule. Both use the `hidraw` linux driver to directly communicate configurations to your keyboard. In most situations, it should be safe to use a *generalized* `udev` rule for all `hidraw` devices, but in other cases where you prefer or are required to restrict access on a device basis, it is possible to create a `udev` rule specifically for your keyboard. 

> [!tip]
> Vial has a magic number that is inserted into the USB serial attribute, so you will only **need one rule for all Vial keyboards** that will be safe to use in conjunction with other `hidraw` device rules.

##### Universal Vial `udev` rule:
For a universal access rule for any device with Vial firmware, write this text to `/etc/udev/rules.d/99-vial.rules` in a *text editor*:

```bash
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{serial}=="*vial:f64c2b3c*", MODE="0660", GROUP="users", TAG+="uaccess", TAG+="udev-acl"
```

You can replace the group with any that you require on your operating system, but the `user` group should work on most distributions of Linux.

In order for the rule to take effect, you must ==reload udev== (explained below) or ==restart== your computer.

##### Generalized VIA `udev` rule:
For a rule that allows users to access **all** `hidraw` devices, write this text to `/etc/udev/rules.d/92-viia.rules` in a text editor. ==(Note that it is written viia with two 'i', it is not a typo)==.

```bash
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", MODE="0660", GROUP="users", TAG+="uaccess", TAG+="udev-acl"
```

Here as well, you can replace the group with any that you require on your operating system, but the `user` group should work on most distributions of Linux.

In order for the rule to take effect, you must ==reload udev== (explained below) or ==restart== your computer.

##### Device-specific `udev` rules:
###### Finding the vendor and product IDs:
Configuring device specific `udev` rules will require knowing the **USB vendor** and **product IDs** of your keyboard. The easiest way to find them is using the `lsusb` command. Most majour Linux distributions include `lsusb` but you may need to install it. This command will list information about all of your connected USB devices. Here's is a sample output for the Keychron Q2 Revision 0110:

```bash
Bus 001 Device 049: ID 3434:0110 Keychron Keychron Q2
```

- The first four hex numbders next to `ID` is the ==vendor ID==.
- The following next four hex numbers, after the `:` is the ==product ID==.

So in this case, the Keychron Q2's **vendor ID** is ==3434== and it's **product ID** is ==0110==.

###### Creating the `udev` rule:
To create a rule for your specific keyboard, use this template:

```bash
# Name of your keyboard
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{idVendor}=="XXXX", ATTRS{idProduct}=="XXXX", MODE="0660", GROUP="users", TAG+="uaccess", TAG+="udev-acl"
```

Replace the **vendor and product ID** with the ones you found for your keyboard using `lsusb`. You may also specify a different group if required. Write this rule to `/etc/udev/rules.d/99-vial.rules` as **root**. 

In order for the rule to take effect, you must ==reload udev== (explained below) or ==restart== your computer.

The following is an **example** `udev` rule for the Keychron Q2:

```bash
# Keychron Q2
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", ATTRS{idVendor}=="3434", ATTRS{idProduct}=="0110", MODE="0660", GROUP="users", TAG+="uaccess", TAG+="udev-acl"
```

##### Reloading udev:
In order for your new `udev` rules to take effect, you must reload the `udev` rules. The standard way to do this is to run the following commands as root:

```bash
sudo udevadm control --reload rules
sudo udevadm trigger
```

> [!tip]- Useful Link about this
> [Setting your keyboard Udev rules in Linux](https://get.vial.today/manual/linux-udev.html)