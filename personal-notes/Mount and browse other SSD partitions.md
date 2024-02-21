---
dg-publish: true
---
##### Get your disk's partition info:
1. First of all you have to create a mountpoint to mount the drive. For example go to your ==$HOME== directory to create a **mount directory** which will serve as a **mount point** for the drive.
	```bash
	mkdir ~/mountpoint
	```
	> [!tip] 
	> Above we have named it to **mountpoint** but you can name it anything else.
2. Now you should find the name of the partition/directory to mount. You can do this with the command `sudo fdisk -l`. This will ==list all the partitions of the disk==.
	```bash
	sudo fdisk -l
	```
	> [!example] Here's an example output:
	> ```bash
	> garohypr ~ → sudo fdisk -l
	> [sudo] password for garohypr:
	> Disk /dev/nvme0n1: 953,87 GiB, 1024209543168 bytes, 2000409264 sectors
	> Disk model: SKHynix_HFS001TEJ9X115N
	> Units: sectors of 1 * 512 = 512 bytes
	> Sector size (logical/physical): 512 bytes / 512 bytes
	> I/O size (minimum/optimal): 512 bytes / 512 bytes
	> Disklabel type: gpt
	> Disk identifier: 942AB9D4-2457-410F-9138-245AC5566E1E
	> 
	> Device             Start        End    Sectors   Size Type
    > /dev/nvme0n1p1      4096    2052095    2048000  1000M EFI System
    > /dev/nvme0n1p2   2052096  980160511  978108416 466,4G Linux filesystem
    > /dev/nvme0n1p3 980160512 2000408575 1020248064 486,5G Linux filesystem
	> ```
	> Above is an example of my actual partitions. I am using the **/dev/nvme0n1p3** and my boot partition is **/dev/nvme0n1p1** whereas my other Linux partition is **/dev/nvmeon1p2**
	
##### So now let's mount a partition from the example above:
- **Mount** the **drive/partition** to our newly created **mount point**:
	```bash
	sudo mount /dev/nvme0n1p2 ~/mountpoint
	```
	This will ask for your **sudo** password and then the drive will be mounted. 

##### Let's browse and access the files:
> [!warning] 
> You need enter into **sudo su** to access or browse the files from the other partition because the files are **owned** by **an other user**. Or else the permissions will be denied.

- Type `sudo su` and enter to sudo mode in your terminal. 
- Now you can freely **access, browse and open** the **files** from the other partition.

This way you can access and check the files from the other partitions, without having to restart your computer and entering to your other Linux partition.
