---
dg-publish: true
---
> [!tip]
> This way you will **create** a **folder**, which you will define as your PATH or **one of your PATHs**, and whatever script you put into it, can be run from your terminal **only** by **typing** the **name** of the **script**.

##### How to do this?
 - Let's suppose that the name of our script is:
 > garo.sh
- Now let's **create** a **directory** wherever we wat, for all of our personal **scripts**. For example, let's **create** a dir in our ==$HOME== folder and let's call this directory:
> .g-scripts

> [!tip]
> You can create the scripts both in a hidden or a normal folder. I prefer to put them in a hidden folder, for which I put "**.**" to the beginning of the folder name.

- Now **copy** your script, ==garo.sh==, to the **newly created directory**, .g-scripts.
- Make sure that your **script** is **executable** with this command: 
	```bash
	sudo chmod +x garo.sh
	```
###### Let's add our new PATH directory to .bashrc:
- Now **open** your **.bashrc** file to edit it and **add** your new PATH directory to the **PATH entry**:
	```bash
	nano ~/.bashrc
	```
- Go to the end of the file and **add this line** to the file:
	```bash
	export PATH="~/.g-scripts:$PATH"
	```
- **Save** it and **close** it. 
- **Close** and **reopen** your terminal.
- **Check** the currently **used PATH** directories with the command below:
	```bash
	echo $PATH
	```

Now when you open the terminal, no matter in which directory you are, if you type `garo.sh` , this will execute the command as if it is a *built-in terminal command*. 

> [!tip] Delete .sh extension
> If you want, you can delete the .sh extension at the end of the file name. This way, you can run the command as `garo` instead of `garo.sh`.

##### For SUDO:
###### First way:
The method above ~~works only~~ for commands that needs to be run ~~without~~ sudo. If you try to run it with **sudo**, you will receive the following error:
```bash
sudo garo.sh
[sudo] password for username:
sudo: garo.sh: command not found
```
But if you still want to or need to run it with sudo such as `sudo garo.sh`, this will **not** work because ==sudo does not share the same PATH directory as the user==. In this case, you have to **add** the script to **one of the root PATHs** such as:

`usr/local/bin`

To do this, let's say that it is in the `~/.g-scripts` directory, then open the terminal and **execute** this command:
```bash
sudo cp ~/.g-scripts/garo.sh /usr/local/bin
```
The command above **copies** the `garo.sh` command to the **sudo PATH**. Now when you run this command **with sudo**, you will see that **it will work** perfectly. *To check the details of the settings of sudo, you can observe the sudoers file*:
```bash
sudo nano /etc/sudoers
```
###### Second Way:
As an **alternative way**, which can be **easier** also, you can create a directory. So let's say that you want to **add** to your **sudo PATH** the directory below: 
> /home/username/.g-settings

To **add** this **folder** to your *sudo secure path*, **execute** `sudo visudo` in terminal. This will open the `/etc/sudoers` with **nano** in a way that you can write. In the opened file, **search** for this **line**:

```bash
## Uncomment to use a hard-coded PATH instead of the user's to find commands
#Defaults secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
```

And **uncomment** the ==Defaults== line and **add** the **directory** of your PATH to it. So the final result should look like this:

```bash
## Uncomment to use a hard-coded PATH instead of the user's to find commands
Defaults secure_path="/home/username/.g-settings:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
```

**Save** the file with ==Ctrl+S==.

After doing this, you don't need to copy the **scripts** to root folders anymore, but you **can keep** them in your ==$HOME== directory.  This *can be easier* for you to manage your scripts.

> [!warning]
> I tried to use ==~/== to as the absolute path, but it did not work. Instead, use ==/home/username/== to direct to your **home directory**.

