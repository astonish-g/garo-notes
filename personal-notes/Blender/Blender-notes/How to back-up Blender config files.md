---
dg-publish: true
---
The corret way of using Blender **back-up** and **exporting** your **user prefs** should be done from the ==~/.config/blender== folder.

- Navigate to **~/.config/blender/4.0/**
> [!warning] 
> Note that the 4.0 is the version number. So it may vary according to the Blender version that you are using.

- In this folder you will see **two** folders at least: **/config** and **/scripts**.
- You **only** want to **export/copy** the **/config** folder as it includes your ==userpref.blend== file which includes:
	- Your **theme** set-up.
	- Your **shortcuts**.
	- I am not sure but I suppose your **startup file**.
	- Your **quick menu** set-up.

You don't need to copy or export anything else. In the other computer or your new Linux installation, it is enough that you **copy** these files, in the **~/.config** folder, **with the same folder hierarchy**. 

> [!tip] Importing user prefs to a newer version of Blender
> If you have installed a **newer version of Blender**, you can **change** the **version number in the folder hierarchy** that you will be creating in your **~/.config** folder. 
> 
> Unless there has been **huge** changes between the version changes, it should work without problems. I did it between **v3.6 and v4.0** and I had **no issues**.