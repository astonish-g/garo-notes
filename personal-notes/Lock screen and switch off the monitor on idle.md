---
dg-publish: true
---
##### Needed apps:
- [[Swaylock]]
- [[Swayidle]]

##### How it works?
Basicly how this combination works is:
- **Swayidle** is **run** on **startup** with script on Hyprland config. You can call it **lockscreen.sh**. Like this:
	```bash
	# Start swayidle lockscreen script
	exec-once = ~/.config/hypr/scripts/lockscreen.sh
	```
- When the computer goes idle, it can execute commands.
- So on the script, we put an idle time and we tell it to **execute Swaylock** after an **idle period**.
- Then again, if the idle **continues longer** again inside the script, it executes an other command that turns the **display off**.
- On the last part of the script, when the **mouse** or the **keyboard** is **touched**, then it turns back the **display on**.

> [!warning]
> Remember to **make** the **lockscreen.sh** script **executable** for it to work!
###### lockscreen.sh script:
```bash
#!/bin/bash

if [ -f "/usr/bin/swayidle" ]; then
  echo "swayidle is installed."
  swayidle -w timeout 300 'swaylock -f' timeout 360 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
else
  echo "swayidle is not installed."
fi;
```
