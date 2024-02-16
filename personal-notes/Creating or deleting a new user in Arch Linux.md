---
dg-publish: true
---
Below you can find the step-by-step guide to create a new user in Arch Linux, with it's home folder and also with root priiledges.
##### How to do it?
- Obviously, open your terminal.
- Type and execute `sudo useradd -m -G wheel -s /bin/bash your_username`
	Above, type the ==new user name== that you want to create, instead of `your_username`.
- Then type and execute `sudo passwd your_username`. 
- Let's say that your **new username** is called *garoi3*, then during this operation, your terminal will look like this:
```bash
[garohypr ~]: sudo useradd -m -G wheel -s /bin/bash garoi3
[garohypr ~]: sudo passwd garoi3
New password:
Retype new password:
passwd: password updated succesffully
[garohypr ~]:
```
##### Now let's add this user in sudo Group:
You should enter the command below to put the **new user**, ==garoi3== to the **sudo Group**:

> [!warning]
> The process given below includes several commands to enter. A single mistake will lead to fauly or indefinite results.

```bash
echo "garoi3 ALL= (ALL)ALL" &gt;&gt; /etc/subdoers
```

After this command, your new user, in this case **garoi3**, should be the part of the sudo Group.

##### How to delete a user?
- To delete a user, just use the command `userdel` like in the example below. Let's say that the user that we **want** to **delete** is called ==garoi3==, then we should type and execute this command:

```bash
sudo userdel -r garoi3
```

This command will **remove** the ==user account, it's associated files and directories, as well as the user's home directory and mail spool.==
###### What is the -r flag of userdel command?
By default, userdel command does **NOT** remove the user's **home directory** or mail spool. To remove these files and directories, you **should use** `-r` option **with** `userdel` command.