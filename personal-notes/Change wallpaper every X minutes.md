---
dg-publish: true
---
> [!tip] You need to download **swww** for this to work with `yay swww`
##### Explanation from Arch-Wiki:
**Create** the following **script** in `~/.config/hypr/scripts/swww-random` and make sure that it is ==executable==.

```bash
#!/bin/bash

# This script will randomly go through the files of a directory, setting it
# up as the wallpaper at regular intervals
#
# NOTE: this script uses bash (not POSIX shell) for the RANDOM variable

if [[ $# -lt 1 ]] || [[ ! -d $1   ]]; then
	echo "Usage:
	$0 <dir containing images>"
	exit 1
fi

# Edit below to control the images transition
export SWWW_TRANSITION_FPS=144
export SWWW_TRANSITION_STEP=2
export SWWW_TRANSITION_TYPE=random

# This controls (in seconds) when to switch to the next image
INTERVAL=300

while true; do
	find "$1" \
		| while read -r img; do
			echo "$((RANDOM % 1000)):$img"
		done \
		| sort -n | cut -d':' -f2- \
		| while read -r img; do
			swww img "$img"
			sleep $INTERVAL
		done
done
```
Next **create** a new **folder** to store **background images**, something like `~/.config/hypr/backgrounds` should work fine, and populate it with any images you want.

After doing all this, call the script from the **hyprland.conf**
```bash
...
exec-once = swww init
exec-once = ~/.config/hypr/scripts/swww-random ~/.config/hypr/backgrounds
...
```
##### An other option from this [link](https://forum.garudalinux.org/t/change-wallpaper-on-sway/30377/2):
**Open** your **Hyprland** configuration file and add this entry to **your** configuration file:
```bash
exec-once = sleep 1; swww init; sleep 1; while true; do swww img /home/garo/Pictures/catppuccin-wallpapers/$(ls /home/garo/Pictures/catppuccin-wallpapers | shuf -n 1) --transition-fps 30 --transition-type=wipe --transition-bezier=0,0.84,1,1; sleep 600; done
```
The **config** above will **change** the **wallpaper every 10 minutes**. You may need to **change** the **directories** if you have a different user name.