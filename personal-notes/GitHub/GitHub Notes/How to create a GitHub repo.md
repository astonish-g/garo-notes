---
dg-publish: true
---
# How to use GitHub! 
### Install git and prepare it

If it isn't already installed, you should first install git with the command `sudo pacman -S git`.

Then in order to use _Git_, you need to set at least a name and email:

```bash
git config --global user.name "Astonish"
git config --global user.email g******git@gmail.com
```

Then you should set the default branch name with this command:

```bash
git config --global init.defaultBranch main
```

Then you should install GitHub-CLI with this command: `yay github-cli-git` to be able to log-in.

Then log-in to your Github account with `gh auth login` and authoriz it with https from the web when prompted in terminal.

### Create a folder with your repo files

First of all you should create a local directory, wherever you want in your computer to create a git repository.


> [!NOTE]
  > Atention that _git_ and _github_ are two different things. _Git_ repository is the `.git/` folder inside a proect. This repository tracks all changed made to files in your project's hisory.
  > 
  > _GitHub_ on the other hand, is a cloud service to host your _git_ project. There are also other alternatives like _Gitlab_. So, git repository **is not equal to** GitHub.
  > 
  > Inside this folder put all of the files, folders..etc that you want to host.

### Start the Git repository

After doing all of the steps above succesfully, from the terminal, navigate inside your folder. To the root directory of your _Git_ repository. It is the main folder that will be uploaded to _GitHub_. From inside that folder type this comnmand:

`git init -b main`

### Add files to the repository

Your **local** git repository is created succesfully. By using the command `git status` you can see the tracked and untracked files. Since the repository has just been created, all the files will be untracked. Now you can add the files that you have in your folder, which you want to have included/tracked in your repository manually with the command `git add <name of the file>`. 

For example `git add blender.md`. Or if you want to add them all, you can type `git add .` and now if you try again the `git status` command, you will see that all of your files are in the tracked, _Changes to be committed_ list.

### Commit the files that needs to be pushed to the Git repository

Now that we have selected the files that needs to be included in our git repository, it is time to commit those files for the first time. You can use the command `git commit -m "my first commit"` to commit the files. 

Remember to add `-m "<some comment>"` or else the commit will fail because it has no comments or explanations.

### Create a Github repository

1. Go to the GitHub webpage and to the repository section of your account and click the green `NEW` button to add a new repository. 
2. There after you choose all the options you want, select the name..etc and create the repository. 
3. The page will lead you to a web page where it will explain how to push your already existing local repository in the second section. Copy and paste those three lines and your local repository will be copied to the cloud GitHub page. That web page doesn't appear if you choose to create the repo with readme.md. In such case, follow the step below.
  
> [!NOTE]
Do not choose to create a README.md file while creating a repository because then when I try to push my commits for the first time, I have always had a problem. I don't know why. Till I find the reason, do not use it.

### After creating the reposiory, do this first:

- Navigate to the directory of the repository's root folder in your terminal

- type these commands

```bash
git remote add <chose an alias for your github repo url><your github repo url>
git branch -M main
git push -u origin main
```

Here's an example:

```bash
git remote add origin https://github.com/astonish-g/bash-scripts.git
git branch -M main
git push -u origin main
```

In the example above, origin is chosen as the alias for the github repo's url. You can set any name. And then the link to the github repo is copied on it. Then you choose the main branch for it and push your files to the repo for the first time.

### How to apply and push modifications?

Well, inside your repository, after you made the changes, add the files that you want to commit again, with always `git add <file name>` command or `git add .` to add all the modifications and commit the added files with `git commit -m "<your comment>"` and finally push it with `git push -u origin main` command.

### How to use the same repo, with the same user on two different computers?

- First clone the repos in a directory where you want to keep the work.

- Sign in to github with **github-cli-git** tool that you had downloaded earlier.

- Find out the used **user.name** and the **user.emai** for the git global with `git config --list` command.

- Set the global **user.name** and the **user.email** like the other computer with these commands. You had the necessary information for the user.name and the user.email as explained on the previous list item. So use these commands:

```bash
git config --global user.name "chosen username"
git config --global user.email <chosen user email>
git config --global init.defaultBranch main
```

- After completing these steps, you can start pushin to the GitHub repository from the other computer too.
