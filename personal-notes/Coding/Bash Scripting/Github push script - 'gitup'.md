---
dg-publish: true
---
Below is a very simple *bash script* that I created for myself, to push my *git* changes to my **GitHub repository**.
##### What does this script do?
1. It **adds** all the untracked files to the **git track list**. Also adds all the modified files to the git track list.
2. Then **commits** all of these changes with the message "push".
3. Finally **pushes** all of these tracked files to the **main repository**.

##### How to use it?
1. Open your terminal and **browse** to your **git folder**.
2. Inside the folder, type and execute the command `gitup`. This is the name of the bash script file in my **$PATH** directory. If you gave it an other name, then you should use that name as the command. 
##### Source code:
```bash
#!/bin/bash

# Add newly modified files to commit
git add . &&

# Commit the modification to Git
git commit -m "push" &&

# Upload/push to Github repo the modifications
git push -u origin main
```

