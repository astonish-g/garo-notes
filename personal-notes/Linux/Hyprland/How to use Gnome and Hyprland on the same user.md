---
dg-publish: true
---
> [!warning] 
> I am still not sure how necessary is this for me to run them both, with my useage. It may be necessary for screenshot, but I am not sure, I still have to learn more about this.

When you install ==both== **Hyprland** and **Gnome** it works pretty well together. The **only** thing you **may need** to **change** (for now this is the only issue I found) are the ==xdg-portals==. 

They say that this is **only necessary** for **screen-sharing** but I don't like to receive weird *errors* on **terminal** when I run an app. 
###### What is the solution?
They advice you to:
- **Kill** the **xdg-desktop-portal-gnome** when you log in **Hyprland**.
- **Kill** the **xdg-desktop-portal-hyprland** when you log in to **Gnome**.

I still have to do this, but I was thinking of **adding** and **exec** script to **hyprland configuration** to run each time that I **start** hyprland.

**For Gnome**, I still don't know. I have not been using it for a long time. But I belleive that I can **create** a small **bash script** that **kills** hyprland xdg-portal. Then I can search and find **how to add scripts to Gnome startup**. I am sure that there is a file where I should **add** the bash script path, and it will run it everytime I start Gnome. But I have to find it and learn.

This way, **you won't have to use any scripts manually** when you start Gnome or Hyprland.