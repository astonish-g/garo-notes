---
dg-publish: true
---
## Sections
- **Formatting - File unrecognized**
- **Conceal**
- **Comment multiple lines**
### Temporary Fix for the Json files

#### Formatting - File unrecognized

When you open a json file and if tree-sitter doesn't recognize it as a json file, you can use the command `:set filetype=json` for neovim to start formatting it.
#### Conceal

The reason why you see the json commands in the config files without `" "` and when you move your cursor line to a line, and see `" "` appear, it is because you have your neovim `opt.conceallevel` set to 2 or 3 also it depends on `cursorconceal` settings. You may need that setting for some plugins such as indent or markdown. To fix the issue in json file, you should execute `setlocal conceallevel=0` and it will fix it.

##### How to comment multiple lines on neovim?

 - Select the first character of your block.
 - Press Ctrl + V ( this enters in visual selection mode )
 - Type j for each line more you want to be commented.
 - Type Shift + i (like I for "insert at start at start")
 - Type # and you will see the modification appearing only on the first line
 - IMPORTANT LAST STEP: Press Esc key ( NOT Enter key) and voilà!

 **And to delete multiple comments:**
 
 - Go again to the beginning of the line and press Ctrl + V
 - Type j for each line more you want to be uncommented
 - And press x.

##### A good video tutorial about Neovim

[Neovim Video Tutorial](https://www.youtube.com/watch?v=Mtgo-nP_r8Y)