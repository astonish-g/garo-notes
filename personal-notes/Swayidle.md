---
dg-publish: true
---
##### What is it?
It is an **idle management daemon** for **Wayland**. It is **compatible** with any Wayland compositor which implements the ==ext-idle-notify== protocol. 

It **listens** for **idle activity** on your Wayland compositor and **executes tasks** on various idle-related events. You can specify **any number** of **events** at the **command line** and in the **config file**.
##### How to install?
Install it with `yay swayidle`

##### Where should the config file be placed?
- XDG_CONFIG_HOME/swayidle/config
- $HOME/swayidle/config

##### How to use?
You have to create a **config** file with the entries that you see in the swayidle manual page. You can also **create** a **script** for swayidle which executes **different commands** when the **set times** are reached. An **example** of ==swayidle script== which I am planning to use:
```bash
#!/bin/bash

if [ -f "/usr/bin/swayidle" ]; then
  echo "swayidle is installed."
  swayidle -w timeout 300 'swaylock -f' timeout 360 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
else
  echo "swayidle is not installed."
fi;
```
###### Explanation of the above command:
- It checks if swayidle is installed and it gives messages according to the result.
- If for 300 seconds, the computer was idle, then it will run **Swaylock** with parameter **-f**.******
- After 360 seconds of **idle**, the script will **switch OFF the monitor**.
- If you touch the **mouse** or the **keyboard**, it will **switch ON the monitor**.

> [!warning] 
> You should make this script **executable** and **run** it on **startup** on your Hyprland **config** file for this to work.
###### An other example from the manual page:
**config file:**
```bash
swayidle -w \\
	timeout 300 'swaylock -f -c 000000' \\
	timeout 600 'swaymsg "output * power off"' \\
		resume 'swaymsg "output * power on"' \\
	before-sleep 'swaylock -f -c 000000'
```

##### Commands to use with this command:
==-C :== You can choose a different config file to use, to keep your **$HOME** folder clean
==-w :== Wait for command to finish executing, before continueing. Helpful for ensuring that a *before-sleep* command has finished before the system goes to sleep.
> [!note] 
> Using this option causes **swayidle** to **block** until the command finishes.


##### Manual Page:
For more detailed info on the useage of **swayidle**, check the [man page](https://github.com/swaywm/swayidle/blob/master/swayidle.1.scd)

##### Useful links to study:
- [Arch-wiki Sway page](https://wiki.archlinux.org/title/Sway)
- [How to prevent swayidle from executaion while watching a movie](https://stackoverflow.com/questions/68694093/how-to-prevent-swayidle-from-execution-while-watching-a-film)



