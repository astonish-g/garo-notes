---
dg-publish: true
---
<strong>Remember that to copy/paste in terminal, you should do it only with the key combination:</strong>

> **CTRL + SHIFT + C**
> **CTRL + SHIFT + V**

- <strong>Install EndevourOS without DE</strong>
- <strong>Install thru github the Hyprland-V3</strong>
- <strong>Install Nemo and Nemo-fileroller</strong>

> Put nemo to 0.82 opacity, and hide the status bar and menu bar. Put the icon zoom to 200% and this way it will be very beautiful, MacOS like.

> Also if it is not set, remember to put archive manager pop-ups of Nemo to floating window rule.

- <strong>Download and install Nordzy-Yellow Icon</strong>

> To change the icon theme, open:
> **GTK Settings app**
> and change the icon theme.

- <strong>Replace:</strong>

> **\~/.config/hypr **folder with the** modded hypr folder**
> **\~/.config/cava **folder with the** modded cava**
> **\~/.config/btop **folder with the** modded btop**
> **\~/config**

- <strong>Change:</strong>

> **\~/.config/neofetch** folder with the **modded neofetch** folder

- <strong>Install neovim</strong>
- <strong>install nvchad by copying:</strong>

> modded **\~/.config/nvim** to **\~/.config**

  - <strong>Add modded catppuccin theme for nvchad by taking it from the modded:</strong>

> **\~/.local/share/nvim/lazy/base46/lua/base46/themes**
>
>the name of the modded catppuccin theme is:
>
> **catppuccin-garo.lua**

  - <strong>Install zsh shell:</strong>

> **sudo pacman -S zsh**

  - <strong>Install oh my zsh with this command and after the installation, it will set your default shell to zsh:</strong>

> sh -c "$(curl -fsSL [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](<https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh>))"

  - <strong>Install powerlevel10k fonts from the github page and place them into:</strong>

> **\~/.local/share/fonts **
> if the fonts folder doesn't exist, create it. Do not change any font on your terminal yet.

  

- <strong>Install powerlevel10k with this command on terminal:</strong>

  

> git clone --depth=1 [https://github.com/romkatv/powerlevel10k.git](<https://github.com/romkatv/powerlevel10k.git>) ${ZSH\_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

>

> then set:

>

> **ZSH\_THEME="powerlevel10k/powerlevel10k"**

>

> in **\~/.zshrc**

  

- <strong>Log out and log back in for shell changes to take effect.</strong>

  

- <strong>Open terminal and it will guide you for the powerlevel10k configuration, finish the configuration.</strong>

  

- <strong>Replace:</strong>

  

> **\~/.config/foot** with the modded **\~/.config/foot**

>

> This will change the look of the terminal as I like.

  

- <strong>Install firestorm viewer from the website and with the .install.sh script. Then install those two files to be able to open the firestorm:</strong>

  

> **sudo pacman -S glu**

>

> **yay -S libxcrypt-compat**

  

- <strong>Install webapp-manager:</strong>

  

> **sudo pacman -S webapp-manager**

>

> **check Librewolf tab if you have problem with web-app theme.**

  

- <strong>Install Blender and replace the theme with catppuccin theme and plug-ins:</strong>

  

> **Download and install it manually.**

>

> **macchiato\_peach or frappe\_peach **theme is nice.

>

> Set the **vertex** size to **7 px** in:

>

> **Theme Settings > 3D Viewport**

>

> While manually installing, I installed Blender into

>

> \~/.local/share/blender

>

> and the settings folder is inside the folder. Just replace the stock 3.6 with your own 3.6 pref folder.

  

- <strong>Install Gimp and Inkscape:</strong>

  

> **sudo pacman -S gimp inkscape**

  

- <strong>Install LibreWolf with:</strong>

  

> **yay librewolf **

>

> <strong>IMPORTANT: and choose the -bin version if you don't want to complie it. It was taking almost 1 hour and it didn't finish.</strong>

>

> and use this for your **web apps**

>

> <strong>IMPORTANT: </strong>If your web app is light themed instead of dark., this is probably because **fingerprintingprotection** is enabled. To disable it, press:

>

> **ALT**

>

> and the menu bar will be visible. Go to:

>

> **Edit > Settings **

>

> and go to **Librewolf tab** and **disable it**.

>

> Then go to the themes tab and set dark theme.

>

> I was unable to go back to the normal window, so just for security, from the menu I opened an other tab and then I closed the web app, it worked very well.

>

> <strong>Also</strong> from this settings menu, <strong>disable check spelling.</strong>

  

- <strong>Install WebCord for discord:</strong>

  

> **yay webcord**

>

> download the **webcord-vencord-git version**

  

- <strong>Copy the wallpapers to:</strong>

  

> **\~/Pictures/wallpapers **

>

> folder. The rice uses this folder for wallpapers.

  

- <strong>Set dark theme for gtk themes with this command from terminal:</strong>

  

> **gsettings set org.gnome.desktop.interface color-scheme prefer-dark**

  

- <strong>Install these two firefox extensions:</strong>

  

> **ZenMate Free VPN**

>

> **Adblock Ultimate**

  

- <strong>Install cmatrix:</strong>

  

> **yay cmatrix**

>

> install **cmatrix-git** version

  

- <strong>Install peaclock:</strong>

  

> **yay peaclock**

  

- <strong>Install Pdf Arranger to split pdfs:</strong>

  

> **yay pdfarranger**

>

> you can install the **git version**.

  

- <strong>Activate autoscroll from Firefox settings.</strong>

  

- <strong>Notesnook:</strong>

  

> Increase the font size to see better from:

>

> **settings > editor > font size**

  

- <strong>Enable yay update for git files as well:</strong>

  

> In terminal type:

>

> **yay --devel --save**

>

> And from now on it should update git files as well. To check and update the packages, type:

>

> **yay**

  

- <strong>Install Whatsapp and Telegram as Web-Apps:</strong>

  

> Install them as web apps because Telegram's native app has title bar

  

- <strong>Install auto-cpufreq from the github:</strong>

  

> Install it from the github page with their installation script because they say that the AUR package is unmantained and will cause problems.

  

- <strong>May be try using:</strong>

  

> **CTRL + SUPER + 1 **

>

> **CTRL + SUPER + 2 **

>

> **CTRL + SUPER + 3**

>

> ..etc to **launch** your **fav apps**. So check with **keybindings** if those shortcuts are available.

  

- <strong>How to disable mouse hover focus?</strong>

  

> Go to **hyprland.conf** file in your **.config/hypr** folder and find this variable:

>

> **input**

>

> and in that group change the value of **follow\_mouse** to **0**

>

> but is it buggy? Report back!

>

> Or change the value to 2 if you want mouse focus to change such as scroll will work without click but the keyboard will remain on the old focus until you click on the new window. Actually **2 **seems like a better value for this option.

  

- **Install xfce-polkit**

  

> You can install it from yay with this command:

>

> **yay xfce-polkit**

>

> without this, you can't run gui apps in sudo when needed. This let's you have a dialog to open gui apps in sudo with the dialog to enter the sudo password.