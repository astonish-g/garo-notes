---
dg-publish: true
---
#### Main info:
##### Needed apps:
- [[Swayidle]] - Works together with [[Swaylock]] if you want to lock your screen too. If not, then **it is not necessary**.

##### Auto dimming apps:
You can use one of the apps below if you want but you can also dim the display, with swayidle and terminal commands easily. **Check** the **Solution 1**.
- **chayang** - [git link](https://git.sr.ht/~emersion/chayang) ==can be found on AUR==
- **dim** - [git link](https://github.com/marcelohdez/dim) ==apparently this one you should build manually==

#### Solution 1:
##### Swayidle and Hyprland config file:
- Open your **hyprland config** file.
- **Add** this line to your config file:
	```bash
	# Start swayidle lockscreen script - 30 seconds for dim and 120 seconds for display off
	exec-once = swayidle -w timeout 30 'brightnessctl set 0%' resume 'brightnessctl set 30%'
	```
	The config line below will **dim** the display after 30 seconds of **inactivity** and put the **brightness back** to 30% when you **move** the **mouse** or **press** a **key** on your **keyboard**.
#### Solution 2 - complicated and unnecassary:
##### Locking your screen:
###### Lock your screen manually:
In your **Hyprland .conf file** you can lock your screen manually using a bind as follows: 
```bash
....
bind = SUPER, L, exec, swaylock -f -c 000000
....
```

###### Automatic screen locking and suspend:
Create the following script in `~/.config/hypr/scripts/sleep.sh: 
```bash
swayidle -w timeout 300 'swaylock -f -c 000000' \
            timeout 600 'systemctl suspend' \
            before-sleep 'swaylock -f -c 000000' &
```
Then call the script in the **hyprland .conf** file:
```bash
...
exec-once = ~/.config/hypr/scripts/sleep.sh
...
```

> [!tip] Adjust the timeout periods
> You can adjust the timeout periods by editing the numerical values, in seconds. 300 is 5 minutes, 600 is 10 minutes..etc.

> [!tip] The script must be executable