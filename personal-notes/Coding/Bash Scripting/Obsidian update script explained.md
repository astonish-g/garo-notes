---
dg-publish: true
---
##### What the script does:

- ###### Local
	- **Removes** the **old history** backup folder, called **obsidian-backup-old**.
	- Names the **copy** of the last **garo-notes** which was called obsidian-backup **to** **obsidian-backup-old**.
	- Creates a **copy** of **garo-notes** and calls it **obsidian-backup** which will become the **next obsidian-old** when new info is written and the script is lunched. So it will serve as a checkpoint.

> [!warning] EXCLUDE the .obsidian/plug-ins folder
> Remember to **EXCLUDE .obsidian/plug-ins folder** from your backup, because it may have plug-ins that needs **username and password** informations, or plug-ins that needs token for your GitHub and if you back that up, all that info will be backed up to GitHub. And that is something that you definitely don't want.
> 
> Also if you do, the token that you have given to your plug-in, such as Digital Garden, will be forced to expire to protect your GitHub repos and your token information will be compromised on web. So **remember to add** these folders in .gitignore before making a pull.
> 
> So instead, **exclude** that folder, and create a new note that explains all of your plug-ins and the set-ups so that you can replicate the customizations that you have made.

- ###### OneDrive
	- It should do exactly the same operation done in local folders.

- ###### GitHub
	- You should create the GitHub repository inside the **~/Obsidian/garo-notes** directory.
	- Push and pull from there

- ##### Command arguments:
	- `obsi local` = Updates in local
	- `obsi git` = Updates the GitHub repository.
	- `obsi onedrive` = Updates the OneDrive folder
	- `obsi lg` = Updates local and Github
	- `obsi lgo` = Updates local, Github and Onedrive
##### Update script code:

```bash
#!/bin/bash

ACTION=${1,,}

# make the local backup
if [[ $ACTION == "local" ]]; then
  rm -rf ~/Documents/Obsidian/obsidian-backup-old &&
  mv ~/Documents/Obsidian/obsidian-backup ~/Documents/Obsidian/obsidian-backup-old &&
  cp -r ~/Documents/Obsidian/garo-notes ~/Documents/Obsidian/obsidian-backup &&
  echo "Local backup is completed succesfully!"

# OneDrive backup
elif [[ $ACTION == "onedrive" ]]; then
  rm -rf ~/OneDrive/Obsidian/ &&
  cp -r ~/Documents/Obsidian/ ~/OneDrive/Obsidian/ &&
  echo "OneDrive backup is completed succesfully!"

#Github Backup push sync
elif [[ $ACTION == "git" ]]; then
  cd ~/Documents/Obsidian/garo-notes/ &&
  git add . &&
  git commit -m "sync" &&
  git push -u origin main &&
  echo  "GitHub push is completed succesfully!"

#Local backup + Git backup
elif [[ $ACTION == "lg" ]]; then
  rm -rf ~/Documents/Obsidian/obsidian-backup-old &&
  mv ~/Documents/Obsidian/obsidian-backup ~/Documents/Obsidian/obsidian-backup-old &&
  cp -r ~/Documents/Obsidian/garo-notes ~/Documents/Obsidian/obsidian-backup &&
  echo "Local backup is completed succesfully!"
  cd ~/Documents/Obsidian/garo-notes/ &&
  git add . &&
  git commit -m "sync" &&
  git push -u origin main &&
  echo  "GitHub push is completed succesfully!"

# Local backup + OneDrive + Github
elif [[ $ACTION == "lgo" ]]; then
  rm -rf ~/Documents/Obsidian/obsidian-backup-old &&
  mv ~/Documents/Obsidian/obsidian-backup ~/Documents/Obsidian/obsidian-backup-old &&
  cp -r ~/Documents/Obsidian/garo-notes ~/Documents/Obsidian/obsidian-backup &&
  echo "Local backup is completed succesfully!"
  rm -rf ~/OneDrive/Obsidian/ &&
  cp -r ~/Documents/Obsidian/ ~/OneDrive/Obsidian/ &&
  echo "OneDrive backup is completed succesfully!"
  cd ~/Documents/Obsidian/garo-notes/ &&
  git add . &&
  git commit -m "sync" &&
  git push -u origin main &&
  echo  "GitHub push is completed succesfully!"

#Error message
else
  echo "Please enter a valid argument."
  echo "Use 'local','onedrive', 'git', 'lg' or 'lgo' as an argument."
fi
```

