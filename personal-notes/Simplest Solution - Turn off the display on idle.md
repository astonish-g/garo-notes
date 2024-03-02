---
dg-publish: true
---
#### Needed apps:
- **swayidle** - you an install it with `yay swayidle`
#### How to use?
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