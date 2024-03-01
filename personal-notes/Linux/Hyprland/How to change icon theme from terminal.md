---
dg-publish: true
---
For example let's say that you want to **download** and **install** and **set** the ==Nordzy Yellow Dark== icon theme in **Linux** from terminal. 
###### Follow these steps:
- **Git clone** the **Nordzy** icon theme from there [github page](https://github.com/alvatip/Nordzy-icon) to somewhere on your computer such as **~/Downloads** folder.
- Go to the cloned **Nordzy** directory in your **~/Downloads** folder.
- **Install** the **Nordzy Yellow Dark** icon theme with this command:
	```bash
	./instal.sh -t yellow -c dark
	```
- Once the installation has finished. If you want to find out about the **name** of the **icon theme**, navigate to this directory:
	
	`~/.local/share/icons`
	
	And there you will see a folder called `Nordzy-yellow-dark` and this is the name of the icon theme.
- **Set** the **icon theme** ==from terminal== with this **command:**
	```bash
	gsettings set org.gnome.desktop.interface icon-theme 'Nordzy-yellow-dark'
	```

After these steps, your **icon theme** will be **changed** to **Nordzy-yellow-dark** ==succesfully==.

[Check this useful link](https://askubuntu.com/questions/262868/how-to-set-icons-and-theme-from-terminal) for more information about **changing** ==icon theme== and ==gtk theme== from terminal.