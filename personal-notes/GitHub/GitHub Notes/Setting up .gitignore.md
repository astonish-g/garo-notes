---
dg-publish: true
---
##### What is .gitignore?
**.gitignore** is a file where you put the names of the directories that you want your git repository to ignore. For example, you can use this to stop the git commands to push some folders or files that may have personal information. So the push command, will **ignore** the documentaries that you type in the file.

##### Where to create the .gitignore file?
You should create it in the **root** directory of your git repository. 

>[!tip] Example
>Let's say that ~/Documents/Obsidian is your **git directory**. Then your **.gitignore** file should go inside the Obsidian folder. So the final destination would be **~/Documents/Obsidian/.gitignore** 
>
>Your  Obsidian folder would include these:
>- \<your contents/files/folders\>
>- .git/
>- .gitignore

##### How to put directories or files inside the .gitignore file?
Let's say that inside ~/Documents/Obsidian folder, you want a folder to be ignored. And the folder is ~/Documents/Obsidian/blender/garo/ , then, you have to add the **relative** path to the **root** of your **local git folder**, inside the .gitignore file that you've created. Also let's say that we also want to ignore ~/Documents/Obsidian/vscode/bash.md , in this case, your .gitignore file would look like this:

```bash
blender/garo/
vscode/bash.md
```

##### How to remove a folder that is already inside your GitHub repo?
As we know now, the **.gitignore** file prevents future untracked files from beeing added to the git index and get pushed to the repo. But any files that are currently tracked, that were not in .gitignore on previous commits, will still be tracked by git. So below, we will explore different possibilities to **remove tracked files from the git index after adding them to .gitignore.**

###### Removing a Single File
In order to remove a single file, we first have to add the file name to .gitignore and then run the *git rm* command, followed by a commit:

```bash
git rm --cached <filename>
git commit -m "<Message>"
```

The first command removes the file from the index and stages the change, while the second command commits the change to the branch.

###### Removing a Folder
We can remove an entire folder by first adding the folder name to .gitignore and running the *git* commands:

```bash
git rm --cached -r <folder>
git commit -m "<Message>"
```

==Notice the -r addition to the command, as without it, the command will failt with:==

```bash
fatal: not removing 'folder' recursively without -r.
```

###### Removing All Ignored Files
Here, we're **removing all files** that are currently beeing ignored in **.gitignore**

```bash
git rm -r --cached .
git add .
git commit -m "Removes all .gitignore files and folders"
```

The first command removes all the files from the index. The second command re-adds all the files without those in .gitignore, and the last command commits the change. After these three commands, all the files from .gitignore will be removed from the index.

>[!tip] Useful link about deleting directories or files from your Git
> [Delete files/directories from your git](https://www.baeldung.com/ops/git-remove-tracked-files-gitignore)
