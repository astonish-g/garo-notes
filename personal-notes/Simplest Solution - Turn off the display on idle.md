---
dg-publish: true
---
#### Needed apps:
- **swayidle** - you an install it with `yay swayidle`

#### How to do the easy way:
- **Open** your **hyprland** config file
- **Add** this line to the config file:
	```bash
	# Start swayidle lockscreen script - 120 seconds for display off
	exec-once = swayidle -w timeout 120 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
	```

So the config line above will turn the **display off** after **120 seconds** and turn it back **on** when you **move the mouse** or make a **key press**. 

If you want more **idle** actions, you can add other lines as well:
```bash
# Start swayidle lockscreen script - 30 seconds for dim and 120 seconds for display off
exec-once = swayidle -w timeout 30 'brightnessctl set 0%' resume 'brightnessctl set 30%'
exec-once = swayidle -w timeout 120 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
```

So the config below will **dim**  the display in **30 seconds** and turn the **display off** in **2 minutes**. 

> [!warning]
> Do the solution above. The complicated way is not necessary and brings nothing more.
#### How to do the complicated way:
- **Create** a **script** and call it something like **lockscreen.sh**.
- **Put** it in `~/.config/hypr/scripts`
- **Make** the script **executable** for it to work.
- **Put** the script **into** your **hyprland** **config** file so that it starts on **startup**:
	```bash
	# Start swayidle lockscreen script
	exec-once = ~/.config/hypr/scripts/lockscreen.sh
	```
- **Save** the file and **reboot** for the changes to take effect for the **first time**.
##### lockscreen.sh
- ###### Script:
```bash
#!/bin/bash

if [ -f "/usr/bin/swayidle" ]; then
  echo "swayidle is installed."
  swayidle -w timeout 120 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
else
  echo "swayidle is not installed."
fi;
```
- ###### What it does?
	- When the computer is **idle for 2 minutes**, it turns the **display off**.
	- When you **move** the **mouse**, or **press** a key on the **keyboard**, it turns back the **display on**.

#### Unanswered Questions?
- [[How to use this with a dimmer app]]?
- [[How to disable swayidle while watching a video]]?