---
dg-publish: true
---
##### Use scenario:
I have installed **both KDE** and **Hyprland** **with the same user** and even though I was using the internet connection in KDE, in Hyprland, I was unable to connect to it. It was giving me an error something like:
> Unable to connect because the ssid needs secrets that were not provided (or something like this)

##### How did I fix it?
> [!tip] 
> Apparently the **NetworkManager** automatically reuses an existing connection. In case your existing connection does not have any secrets stored, the new connection attempt will not update the existing connection and fail due to missing secrets. 

Type these in **terminal**:
- `nmcli con delete \<SSID\>`
- `nmcli dev wifi connect <SSID> password "password"`

> [!note]
> If your SSID name includes more than one words that are separated with spaces, then put all the SSID name in coma. For example, **Galaxy S20 Wifi** could be written as `"Galaxy S20 Wifi"`.