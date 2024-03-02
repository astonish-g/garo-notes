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
exec-once = ~/.config/hypr/scripts/swww-random ~/.config/hypr/background
...
```
