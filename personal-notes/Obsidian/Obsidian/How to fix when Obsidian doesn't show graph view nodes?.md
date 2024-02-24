---
dg-publish: true
---
When Obsidian **starts** to **bug** while **showing** the **graph** view, **to fix this**, go to:

==Obsidian Settings > Appearance== 

and in this section, **disable** the **hardware acceleration**. This should sove the issue but then you will loose the GPU acceleration in the app. 


> **If you want to keep the hardware acceleration**, in this case you may have to forget about the graph view - *afterall I am not really using it* - unless I find a different work around.

>[!info] 
>Apparently this is a **graphic driver issue** for now. 

> [!question] How to **force** Obsidian to use **Wayland**?
> Some people are saying that you should force Obsidian to use **Wayland** to fix this issue. Most probably you should add something to the .desktop file, search how to do it. 
> 
> Apparently it fixes issues with Nvidia and electron apps having weird Xwayland issues. Find out how to do and experiment.