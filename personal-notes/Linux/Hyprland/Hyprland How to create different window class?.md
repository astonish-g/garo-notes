---
dg-publish: true
---
##### Creating different window classes in Hyprland:
- So let's say that you are trying to create a window class for alacritty to open only with a special keybinding. So let's say that you have your standard alacritty and you want it to open floating with a different window color, in a precize size and position, with a different border colour when you press a different keybinding.
- Let's say that: 
	- **SUPER+ENTER =** Opens *normal* Alacritty
	- **SUPER+SHIFT+ENTER =** Opens *floating* Alacritty
##### How to do?
1. Create the keybinding with a new class name inside the **hyprlnd** configuration file. For example do this:
	- `bind = $mainMod SHIFT, RETURN, exec, alacritty --class floating`
	So the key binding above, will open Alacritty, instead of it's usual *Alacritty class*, it will open it with the class named *floating*.
2. Then create window rules for that class. For example:
	- `windowrulev2 = float,class:floating`
	- `windowrulev2 = size 500 450,class:floating`
	- `windowrulev2 = center(1),class:floating`
	- `windowrulev2 = bordercolor rgb(f38ba8),class:floating`
	- `windowrulev2 = bordersize 7,class:floating`
	So with the example above, when you press **super+enter**, Alacritty will open normally. If you press **super+shift+enter**, it will open floating, with 500px of width and 450px of height, in the center of the screen, with 7 (pixels?) border.
###### Note:
- When you are defining your window rules and typing the class names, you can type them in two ways:
	1. `windowrulev2 = float, class:floating`
	2. `windowrulev2 = float, class:^(floating)`
	They both seem to work. I don't know the difference. Find out.
###### Note 2:
It is not really related, but if you want, in the example above, want the floating Alacritty terminal to have different colours...etc, you can create a second configuration file in the `~/.config/alacritty/` folder and name it to something else than the default one. Then you can launch the *alternative* Alacritty with the second config file with the `--config-file <path>` flag. Let's say that the second config file is called alacritty-floating.toml, then you can set the *keybinding* in the *hyprland config* file this way:
	`bind = $mainMod SHIFT, RETURN, exec alacritty --class floating --config-file ~/.config/alacritty/alacritty-floating.toml`
