---
dg-publish: true
---
##### Needed apps:
**wev** - an app to register the input and tell the key codes for it. You can install it with `yay wev`.

##### Problem:
By default, in your **Hyprland** config file, if you use symbol keys in keybindings such as:
```bash
bind = $mainMod, -, exec, ~/.scripts/smallgaps.sh
```
may not work. Instead you should find the **key code** or the **symbol name** for that symbol. Instead, you have to write it this way:
```bash
bind = $mainMod, code:20, exec, ~/.scripts/smallgaps.sh
```
or
```bash
bind = $mainMod, minus, exec, ~/.scripts/smallgaps.sh
```
Now this would accept the keybinding and work as intended.

##### How to find the key code or the name?
- **Launch** the app called **wev** in your **terminal**.
- It will open a **checkered** window as well, I don't know what it is used for.
- **Press** the key that you want to **find** out the **code** for.
- Then with the **checkered** window in **focus**, **close** the app with **mod+q**.
- **For example** let's try to **find** out the code for `-` key. This will produce a **long output** and in the output somewhere, you will see something like this:
```bash
[14:     wl_keyboard] key: serial: 14337; time: 6744496; key: 20; state: 1 (pressed)
                      sym: minus        (45), utf8: '-'
[14:     wl_keyboard] key: serial: 14338; time: 6744573; key: 20; state: 0 (released)
                      sym: minus        (45), utf8: ''
```
Above, the word **next** to the **output** ==sym== is the **name of the key** that you have **pressed**. So in this case, it is the **minus** key. 

The **number** next to the **output** ==key== is the **key code** that you can **use** in your **Hyprland** config file.  So here's the **result:**

```bash
code:20
```
or for the **name:**
```bash
minus
```