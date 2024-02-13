---
dg-publish: true
---
**ZSH shell notes:**

- **Getting into a folder with a name with several words on it:** If you want to get into a folder via terminal that has a name that is composed with 2 or more words, you can do in several ways. Let's make an example with an imaginary folder. Let's say the name of the folder is **My New Wallpapers**. To access this via terminal do like this:
	> **cd "My New Wallpapers"**
	> 
	> works or you can type:
	> 
	> **cd My\ New\ Wallpapers**
	> 
	> and this works as well.

- **How to keep the original theme of Oh My Zsh theme?**

	> **Go** to **Home/.zhrc**
	> 
	> and open the file with a text editor. In the file, make sure that this line is this way if the plugin is installed:
	> 
	> **ZSH_THEME="robbyrussell"**
	> 
	> And **restart terminal**.
	> 
	> **Note** that you have to **install** the plug-in **manually** after you get into the ZSH shell.

- **How to change the theme of ZSH shell to Powerlevel10k?**

	> Well in this case, the line in **.zhrc** file should be this way if the plug-in is already installed. Right now on Legion 7 it is installed. On the other hand, on yoga, you should install it :
	> 
	> **ZSH_THEME="powerlevel10k/powerlevel10k"**
	> 
	> And **restart terminal**.

- **How to add full path view on the shell theme command beginning?**

	> You should navigate to this file:
	> 
	> **~/.oh-my-zsh/themes/robbyrussell.zsh-theme**
	> 
	> Then in the file find this line:
	> 
	> `PROMPT+=' %{$fg[cyan]%}%c%{$reset_color%} $(git_prompt_info)'`
	> 
	> and on this line, replace the **c** that I marked in yellow, with **~** and then it will start showing you the full path in the future. You need to change just one character. Save the file and then:
	> 
	> **restart terminal.**

- **How to restart powerlevel10k configuration?**

	> Open terminal and type
	> 
	> **p10k configure**
	> 
	> and the configuration will start