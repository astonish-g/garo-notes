---
dg-publish: true
---
> [!warning]
> Need to update the procedure as I do not do it this way anymore.

Here is how I installed Blender from their website :

1. Download the archive : [https://www.blender.org/download/](https://www.blender.org/download/)
2. Extract it to /opt :

```bash
sudo mkdir -p /opt/blender    
sudo tar -xf blender-3.1.2-linux-x64.tar.xz -C /opt/blender --strip 1
```

3) Copy the "blender.desktop" to "~/.local/share/applications"

4) Edit the "Exec" line of the Desktop file like this :

Old :

```bash
Exec=blender %f
```

New :

```bash
Exec=/opt/blender/blender %f
```

This is it! **OBSERVE WHERE I PLACED BLENDER ON MY VERSION ON LEGION**

Ask me if you have any question! :)