---
dg-publish: true
---
##### Info:
When you install a new Linux OS or Windows on a different partition, GRUB will not see the one of the installations when you update grub. So because of this, you can boot into only one partition.

##### Solution:
- You should disable ==GRUB_DISABLE_OS_PROBER== by going to the file in:
> /etc/default/
- Then open **grub** in this directory with a **text editor** such as **nano**.
- Go to the line where GRUB_DISABLE_OS_PROBER is written and **uncomment** the line and ==make sure== that the value for it is ==false==.
- Save it and then make **grub-mconfig** command from the grub fix help file in your notes.