---
dg-publish: true
---
#### Tags
#onedrive #rclone #sync
#### Content
###### Installation
- First of all create a directory in your home folder where you want to mount Onedrive. 
	`mkdir ~/OneDrive` or navigate to your home folder and:
	`mkdir OneDrive`
	*You can put any name that you desire.*
- Then install **RClone** with:
	`sudo pacman -S rclone`
- When the installation completes, you need to configure rclone with:
	`rclone config` command.
- In the options that will appear, type `n` and press enter for `New remote`
- It will ask you to enter a name for the new remote, type `OneDrive` and press enter to confirm it.
- From the list that opens, search for the number that is for the connection that you want to create, in this case it will be `Microsoft OneDrive` and type the number next to it and press enter to confirm it.
- It will ask for `client id` but it is **not required** so press just enter.
- Then it wil ask for `client secret` which is **not required** either. So just press enter.
- On the next dialog, choose `1` for `Microsoft Cloud Global` and press enter to confirm the selection.
- Then it will ask you if you want to edit advanced config, refuse it with `n` and press enter.
- Then it will ask you if you want to use your browser to automatically authenticate rclone with the remote - in this case OneDrive -. Press `y` and press enter to confirm it.
- Then it will open your web browser to authenticate. Once authenticated, it will ask you to go back to your rclon config in terminal.
- Select `1` for `OneDrive Personal or Business`
- On the next screen, select `1` - seems like it is the only option.
- It will tell you that it found a root type of a personal folder. Press `y` to confirm it.
- It will ask you if you want to keep that OneDrive remote, confirm it with `y`
- Then you can close the configuration by entering `q`
###### Mount the OneDrive Cloud storage to the created directory
- In your terminal, navigate into the directory that you had created for OneDrive.
- Then execute this command:
	`rclone --vfs-cache-mode writes mount OneDrive: ~/OneDrive &`
- Now you will see that your OneDrive files will start to appear in that directory. It may take some time for the items to download and show up inside the folder, so be patient.
- To avoid typing this command on every session of Linux that you start, it is advised to put this command on autostart. So to something like in your hyprland configuration or if you have an autostart file, put in it. You can create also a bash script for it and put that script in your autostart. 
##### Useful Video tutorial:
Check this video tutorial: [Youtube tutorial](https://www.youtube.com/watch?v=u_W0-HEVOyg)
