---
dg-publish: true
---
##### What does this script do?
Well, this is very simple, it is actually just a command, but I saved it as a script in case I forget the command and it is faster to execute it this way. This script **pulls** the changes from the **GitHub repository**.

##### How to use it?
I named my file in the **$PATH** folder as ==gitdown==, so to use this command, navigate to your *git directory* with your terminal. Then **execute** the command `gitdown`. Then the 'script' will pull all the latest changes from the GitHub repository.
##### Source code:
```bash
#!/bin/bash

# Pull changes from Github to local repo folder
git pull origin main
```
