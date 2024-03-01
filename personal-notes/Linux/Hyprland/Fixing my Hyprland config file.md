---
dg-publish: true
---
When I have reinstalled my Linux and imported the dot files. I have noted some issues with the config file:

- It was giving me **error** about th ==first lines== of the config file:
	> This was happenning because on the title, I was using several ##### to comment the lines. But apparently Hyprland config file doesn't support this. On maximum you can put 2 ## to comment lines. So I deleted the extra hashtags, it fixed the issue. 
	
- It told me that the line with **ULauncher** was not a valid config line:
	> The *ulauncher line* was writting with `exec /usr/bin/ulauncher --hide-window` but this is not the correct syntax. To fix it, I had to add `=` adfter `exec` so the line looks like `exec = /usr/bin/ulauncher --hide-window`
	
- There was an error on the **line 67** where there was a default config about  **epic mouse**:
	> I commented out the three lines that was shown as a per device config example and it solved that issue as well. Seems like I am not even using it because I don't have that mouse.
	
- Finally it was giving me an other error about a windowrulev2 at line 192:
	> The error was on the line `windowrulev2 = nomaximizerequest, class:.*`. This is a prewritten line to the config file, so I have no idea why there is the issue, but I will just search for it and check what is the error, may be they have changed something on it. Commenting that line made the error dissappear in the meantime.