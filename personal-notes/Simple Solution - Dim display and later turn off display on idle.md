---
dg-publish: true
---
##### Needed app:
- [[Swayidle]]
- [[Brightnessctl]] - **ONLY** for **IPS** displays

##### How to achieve this?
**Add** the below entry to the **hyprland config** file: 

```bash
# Start swayidle lockscreen script - 30 seconds for dim and 120 seconds for display off
exec-once = swayidle -w timeout 30 'brightnessctl set 0%' resume 'brightnessctl set 30%'
exec-once = swayidle -w timeout 120 'hyprctl dispatch dpms off' resume 'hyprctl dispatch dpms on'
```

##### What does this configuration do?
- **Dims** the screen:
	- After **30 seconds** of **idle** time, it **sets** the display **opacity to 0%**.
	- When you **move** the **mouse** or **press** a **key**, it **sets** the **opacity to 30%**
- Turns the **display off:**
	- After **120 seconds** of **idle** time, this will turn the **display off**.
	- When you **move** the **mouse** or **press** a **key**, it turns the **display on**.

##### How to disable this temporarily while watching videos on Firefox?
You can do this by adding a **window rule** to your **hyprland** config. The **property** that **interests** you is ==idleinhibit==. 

So if you want to **disable** the **swayidle** while watching a youtube movie or using **firefox** in **fullscreen** mode, you should **add** this **windowrulev2** according to the Hyprland-wiki:

```bash
# Ignore dmming and display off for full-screen Firefox
windowrulev2 = idleinhibit fullscreen,class:firefox
```

This will **disable swayidle for fullscreen firefox**. So when you go full-screen with **SUPER+F**, till you get out of full screen mode, your computer will **not** go **into idle**.