---
dg-publish: true
---
##### My method of installing:
>[!tip] New Installation Method
>Below is the new method that I use to **install Blender**.

- Go to the website of **Blender** and **download** it.
- Once downloaded, go to the download folder and **unzip** the Blender.
- **Copy** the unzipped Blender folder into a directory in your **.local** folder. For example to `~/.local/share/blender`.
- **Create** a ==blender.desktop== file in `~/.local/share/applications`.
- **Assuming** that your Blender folder is in `~/.local/share/blender`, with a **text editor** or **VSCode** type these into the **blender.desktop**.
	```bash
	[Desktop Entry]
	Name=Blender
	GenericName=3D Modeler
	Comment=3D modeling, animation, rendering and post-production
	Keywords=3d;modeling;rendering;
	Exec=/home/garohypr/.local/share/blender/blender
	Icon=/home/garohypr/.local/share/blender/blender.svg
	Terminal=false
	Type=Application
	PrefersNonDefaultGPU=true
	X-KDE-RunOnDiscreteGpu=true
	Categories=Graphics;3DGraphics;
	MimeType=application/x-blender;
	```
- If you followed these steps correctly, Blender should appear in your app launcher after completing all those steps.

> [!danger] Type the full path to the Blender folder
> Note that you may need to write the full path of your app folder, in the .desktop file, instead of the relative path. So you may have to write ==/home/username/../blender== instead of ==~/../blender==

---
##### Other method of installing:
> [!warning] Old way of installing
> Below is the old way of installing Blender that I had learned on internet. But lately, I prefer the way above. In case if you are interested, I am keeping this method as well.

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