---
dg-publish: true
---
##### How to install?
Install it with `yay swalock` from the **AUR** packages.

##### How to use?
I think that you have to create a config file, with the entries that you see in the [Swaylock Manual Page](https://man.archlinux.org/man/swaylock.1)

##### Where should the config file be placed?
- $HOME/.swaylock/config
- XDG_CONFIG_HOME/swaylock/config
- SYSCONFDIR/swaylock/config

###### An example config file from [Reddit](https://www.reddit.com/r/swaywm/comments/vc0cxl/my_swayidleswaylock_configuration/):
**Sway config:**
```bash
### Idle configuration
exec swayidle -w \
          timeout 240 '$HOME/.config/sway/scripts/lock.sh' \
          before-sleep '$HOME/.config/sway/scripts/lock.sh'


### Manual Lock
bindsym --release $mod+Control+s exec '$HOME/.config/sway/scripts/lock.sh'
```

**lock.sh:**
```bash
#!/bin/bash

# If idle for 15s, power down the output
swayidle -w \
		timeout 15 'swaymsg "output * dpms off"' \
		resume 'swaymsg "output * dpms on"' &


# Lock screen immediately
swaylock --image ~/wallpaper.png


# Kill the last instance of swayidle so the timer doesn't keep running in background
pkill --newest swayidle
```

In the reddit thread, **the user** who **created** this script is saying that, by **creating** the *second script* **separately** let's you **lock** the screen separately. For more info, check the reddit link above.

###### An other example from [Reddit](https://www.reddit.com/r/swaywm/comments/rnec4g/help_needed_with_swayidle_and_swaylock/)
**Swaylock config file:**
```bash
# lock screen before suspend. Use loginctl lock-session to lock your screen.
exec swayidle -w timeout 300 'swaylock -C$HOME/.config/swaylock/config.idle' timeout 420 'systemctl suspend' resume 'swaymsg "output * dpms on"' before-sleep 'swaylock'
exec swayidle lock 'swaymsg "output * dpms on"&& swaylock' unlock 'kill -s 1 $(pgrep swaylock)'
```
**Config.idle file:**
```bash
grace=5
daemonize
screenshots
fade-in=4
ignore-empty-password
effect-greyscale
effect-blur=10x2
indicator
clock
text-color=blue
```