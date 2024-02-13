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

##### How to delete a folder that is already inside your GitHub repo?
Check this [link](https://www.baeldung.com/ops/git-remove-tracked-files-gitignore) to type the not tomorrow.