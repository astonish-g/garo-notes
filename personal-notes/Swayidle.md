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
You have to create a **config** file with the entries that you see in the swayidle manual page.

###### An example from the manual page:
**config file:**
```bash
swayidle -w \\
	timeout 300 'swaylock -f -c 000000' \\
	timeout 600 'swaymsg "output * power off"' \\
		resume 'swaymsg "output * power on"' \\
	before-sleep 'swaylock -f -c 000000'
```

##### Manual Page:
For more detailed info on the useage of **swayidle**, check the [man page](https://github.com/swaywm/swayidle/blob/master/swayidle.1.scd)

##### Useful links to study:
- [How to prevent swayidle from executaion while watching a movie](https://stackoverflow.com/questions/68694093/how-to-prevent-swayidle-from-execution-while-watching-a-film)



