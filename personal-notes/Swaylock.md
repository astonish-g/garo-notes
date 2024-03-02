---
dg-publish: true
---
> [!tip] Swaylock-effects-git
> Instead of `swaylock`, install `swaylock-effects-git` fork because it has cooler effects that you can use.
##### How to install?
Install it with `yay swaylock-effects-git` from the **AUR** packages.
##### Useful Info:
I think that you have to create a config file, with the entries that you see in the [Swaylock Manual Page](https://man.archlinux.org/man/swaylock.1)
[Swaylock Effects Github Page](https://github.com/mortie/swaylock-effects) 

> [!tip] Bash Syntax Highlight
> If VSCode doesn't recognize the language of the config file and does NOT highlight the colours. You can add `#!/bin/bash/` to the beginning of the file and then your config file will be highlighted correctly. 

> [!tip] Make a [[Wallpaper Script]]
> To make Swaylock work nicer, make a wallpaper script, and make that script copy the curren used wallpaper into `~/.cache/current_wallpaper.jpg` so this way, you can point swaylock to use it without setting up the image in the config file manually.
> 
> [Watch this video](https://www.youtube.com/watch?v=ptmiPG_V4u8&t=601s) for more info

##### How to use?
- Create the config **directory** `~/.swaylock`.
- Create it **config file** and call it ==config==.
- Then **go** to the [swaylock man page](https://man.archlinux.org/man/swaylock.1).
- By reading the manual, **add** the **entries** that you **want** with their properties to the config file, one on top of the other.
- For **extended features** coming with the **swaylock-effects-git** fork, go to the [Github page](https://github.com/mortie/swaylock-effects) of this fork.
- Once done, to **test** it, **save** it and in your **terminal**, ==run:== `swaylock` command.

> [!note] 
> You should use `=` when entering the values for the properties/entries. I did not try with `:` but I know that it works with `=`.
> 
> For example if in the *manual page* it is written as:
>  `--indicator-radius <radius>`
>  then you should write it in your config file as: 
>  `indicator-radius=150`. 
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

##### Useful links to study:
- [Lock screen config in sway](https://code.krister.ee/lock-screen-in-sway/)