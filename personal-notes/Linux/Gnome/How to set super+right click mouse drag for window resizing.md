---
dg-publish: true
---
By default, [[Gnome]] does not resize windows with ==SUPER+Right Mouse Click== like the window manages. Since I am used to this with the [[Hyprland]] and I like using my computer this way, I searched and found the way to do it on Gnome as well. 
###### How to do this? 
- Open your terminal
- Execute the command below in terminal:
	```bash
	gsettings set org.gnome.desktop.wm.preferences resize-with-right-button rue
	```

After executing this command, you can now start **resizing** your **windows** with **SUPER+Right Mouse Click and drag** like in the window managers.

[Useful link about this subject](https://unix.stackexchange.com/questions/28514/how-to-get-altright-mouse-to-resize-windows-again#:~:text=In%20more%20recent%20gnome%20versions%20%28e.g.%2C%20gnome-shell%29%2C%20you,alone%20will%20enable%20moving%20%28super-leftdrag%29%20and%20resizing%20%28super-rightdrag%29.)