---
dg-publish: true
---
##### Tags:
#Appimage

##### Content:
###### Problem:
When you try to create a .desktop entry for an **AppImage**, you may realize that it does not appear in your launcher. To solve this, you have to extract the app image first.

###### Solution:
So let's say that we are trying to create a *.desktop entry* for *Obsidian-1.5.3.AppImage*. Here are the steps to follow:

1. Copy the *Obsidian-1.5.3.AppImage* to the directory where you want to place the app bin. For example to *~/.local/share/apps/* and place a temporary directory such as */obsidian-extract* and place the *Obsidian-1.5.3.AppImage* in that directory.
2. In your terminal browse to the directory where you have your *AppImage*.
3. Inside the directory use this command to extract the AppImage: 
	```bash
	./Obsidian-1.5.3.AppImage --appimage-extract
	```
	> [!warning] Give execution permissions first
	> Note that you should give execution permission to the app before doing the step above, or else it won't work. 
1. This will extract all the contents of the file to a */squashfs-root* root folder that it will create in that directory.
2. You can rename the */squashfs-root* directory to anything you want such as */obsidian* 
3. Then place this newly created *folder* to the initial location that you wanted to place your app bin. In our case it was *~/.local/share/apps*
4. Create a .desktop entry in *~/.local/shar/applications*, something like obsidian.desktop
5. In the desktop entry, point the *exec* destinition to the extracted AppImage folder. So it will look something like this: *~/.local/share/apps/obsidian/obsidian* after making sure that the obsidian bin is executable.
6. Do the same for the icon entry as well.
7. Delete the temporary folder that we created in step 1 - */obsidian-extract*
8. You are done. Now you should be able to see this desktop entry in your app launcher.