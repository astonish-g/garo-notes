---
dg-publish: true
---
sudo su  
  
mount /dev/sda4 /mnt 
*this is the partition of your linux installation*  
  
mount /dev/sda1 /mnt/boot/efi 
*this is the partition of the boot files*  
  
arch-chroot /mnt 
*this let's your log to your system from a live usb or an other distro if you dualboot*  
  
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=EnOS  
  
grub-mkconfig -o /boot/grub/grub.cfg

**ATTENTION: you should be sure that on your grub config file, the OS_PROBE is set to FALSE and uncommented!**