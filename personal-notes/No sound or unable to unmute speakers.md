---
dg-publish: true
---
##### Info:
This happenned to me one time when I booted my computer. No matter what I did, my speakers were muted and I was unable to mute it from GUI in the **Pulse Audio Controller** app. 

##### Solution:
- Open your **terminal**.
- Type ==alsamixer== which is a **CLI** tool for **audio**.
- Once the app is open, press **m** key of your keyboard to **unmute** your speakers.

This should **unmute** your **speakers**. This happenned to me once I had a problem with the speakers, and I **resolved** it **this way**. So you can try it. 

For more info, you can check, **Arch Wiki**'s, [Pulse Audio Troubleshooting](https://wiki.archlinux.org/title/PulseAudio/Troubleshooting) section. I found this solution from there.