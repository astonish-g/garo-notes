---
dg-publish: true
---

##### How to open Developper mode inside the app?
- When you press `ctrl+shift+i` this will open the developper mode. This way you can examine, and find out about the .css selectors to modify the snipplets.
- Zooming in makes the developper window splitting from horizontal to vertical. So keep this in mind if you want to have a vertical view for your developper winow.

##### How to apply css mods to Obsidian?
- You should place it into the **/.obsidian/snippets/** folder of your vault folder. For example my vault folder is called *garo-obsidian-notes* so I had to place it in **~/Documents/garo-obsidian-notes/.obsidian/snippets/** and then from the settings you should enable this css snippet. 
- Once applied, from the *Appearance* menu, whenever you make a change to the .css file and save it, it will be updated immediatly.

##### My Hotkeys (some are custom hotkeys):
- **Alt+B =** Hide or show left sidebar. Expand or Collapse
- **ALT+T =** Hide or show tab bar.
- **ALT+SHIFT+T =** Hide or show the title bar. 
- **ALT+Right Arrow =** Hide or show right sidebar. Expand or collapse.
- **ALT+S =** Hide or show status bar.
- **CTRL+B =** Toggle bold.
- **CTRL+Right Arrow/Left Arrow =** Brings the cursor to the end of the next word.
- **CTRL+P =** Enters command mode.
- **CTRL+E =** To toggle between reading and editing mode.
- **CTRL+O =** For quick switching between notes. Press **ctrl+enter** to open on a new tab.
- **ALT+E =** Open Emoji toolbar 😉
- **CTRL+G=** Open graph view
##### Tab Hotkeys and Options:
- **CTRL+enter =** To open a note in a new tab when in quick switcher.
- **Drag the tab outside of the window** to open it in a new window.
- **Pin a tab:** To pin a tab, *right click* on the tab name and select *pin*. All the note links that you click on that note will open in a *new tab*.
- **CTRL+1 =** Jump to the first tabl on the left.
- **CTRL+TAB =** To switch to the *next tab*.
- **CTRL+SHIFT+TAB =** To switch to the *previous tab*.
- **CTRL+W =** Close the *current tab*.
- **CTRL+ALT+W =** Close *all other tabs*.
- **CTRL+SHIFT+W =** Close *window*.
##### How to open a note link in a new window?
1. While viewing the note, **right click** on the link and select **open in new window**.
##### How to move the current note to a new window?
1. Press *CTRL+P* to open the command mode
2. Type *"Move current tab to a new window"*
3. Hit enter.

##### How to type /<example/> type of words in Obsidian?
When you type **\<** and **\>** symbols in Obsidian, they will be considered as html tags and they won't be rendered. So to render them correctly to use in your notes, you should escape them to register them as normal characters. 
- So typing it as `/<example/>` will render it as **\<example\>**

##### How it looks my Obsidian? (Trying to import an image link)
So this is how it looks:

![Obsidian-screenshot](https://i.imgur.com/QsZxOk4.jpg)

You can create a Github repo to store all of your screenshots to add in your Obsidian note files. This way you will never loose them.

##### Emojis do not appear? how to fix?
To fix this, you have to install emoji fonts. Do this to install emoji fonts:
```
sudo pacman -S noto-fonts-emoji
```
And once you install the fonts, it should start rendering the fonts correctly. Enjoy using them 😜

The other plug-in 🔆 is nice too but it is a little bit slow 🙁💔

##### Using an image hosted in GitHub

1. Upload the image / push the image to the Github repository
2. Then once it is in the GitHub repository, instead of clicking on the image and selecting *copy link* open the image in your browser from the GitHub repository.
3. Then **right click** on the image and select *open image in new tab*
4. Then copy the link that the image opens in. Or else it will look like a broken image.