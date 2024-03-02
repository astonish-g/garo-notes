---
dg-publish: true
---
##### Needed apps:
- [[Swaylock]] - Most probably needed for the app to trigger before it goes to lock.
- [[Swayidle]] - Works together with [[Swaylock]].

##### Auto dimming apps:
- **chayang** - [git link](https://git.sr.ht/~emersion/chayang) ==can be found on AUR==
- **dim** - [git link](https://github.com/marcelohdez/dim) ==apparently this one you should build manually==

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