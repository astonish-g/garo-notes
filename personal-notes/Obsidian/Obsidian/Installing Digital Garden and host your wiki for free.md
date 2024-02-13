---
dg-publish: true
---
###### Requirements:
- A Github account
- A Vercel account
- Digital Garden plug-in for Obsidian

>[!warning] Put .obsidian folder in .gitignore
>Remember to put the .obsidian/ folder into the .gitignore file in the root directory of your git repository, or else, your token will be pushed to the GitHub repository and the secret token will be compromised and shared with public.

##### How to make this work?
1. First of all install the Digital Garden plug-in in Obsidian from the Community Plug-ins section.
2. Next you will need a GitHub account. If you don't have this, create one.
3. You'll also need a Vercel account. You can sign-up using Your Github account [here](https://vercel.com/signup) but doing it this way gave me problems. So what I did was, I opened the Vercel account with my email, and then I linked my GitHub account to it.
4. At this step, still, do **NOT** create a repo or a Vercel project yet.
5. Open [this repo](https://github.com/oleeskild/digitalgarden) and click the **"Deploy to Vercel"** button.

![Deploy-to-Vercel](https://raw.githubusercontent.com/astonish-g/garo-notes/main/image-sources/obsidian/github-digital%20garden.png)

6. This will send you to the site of the Vercel and from the Vercel site, you will create a new repository. So give the repository the name you want. Set if you want it private or public access and normally you shouldn't need to make any other changes.
7. Then you need to create an access token to your GitHub Account. You can do it from [this page](https://github.com/settings/tokens/new?scopes=repo). Instead of giving a full access to the repository with the token, for security reasons, it is better to give it [[Fine grained token]] where you can also choose which repository gives access token..etc. 
8. Open your Obsidian and settings for "Digital Garden" and fill in your GitHub username, the name of the repo with your notes that we created in the step 6 (for example in my case notes-wiki) and lastly paste in your token.

![digital-garden setting](https://raw.githubusercontent.com/astonish-g/garo-notes/main/image-sources/obsidian/digital-garden-settings.png)

9. Make sure that you have the green tick next to the Github Authentication. If the icon does not change, seems stuck, browse in different sections of the *Obsidian settings* and then return to the *Digital Garden settings*.
10. You set up the Digital Garden plug-in succesfully. Now we should publish our pages.
##### How to publish your pages?

1. Open the note that will be the home screen of your personal wiki and add two properties to the page. 
	
	`dg-publish`
	`dg-home`
	
	We are putting the `dg-home` property only to the home page and the `dg-publish` to the each page that you want to publish. These two properties should be set to check box and should be set to true or checked. 
2. Then press `ctrl+P` to open the *command menu* and publish your home page by typing *Digital Garden: Publish single note*. This way, the home page has been published.
3. For the other pages, you should only put `dg-publish` property. **Unfortunately** you have to do this manually for all the pages that you want to publish. And in case if there are any pages that you don't want to publish, you can uncheck the property. So now, add the `dg-publish` property to all the other pages one by one and remember to add this to the new pages as well. *Note* that you don't need the `dg-home` property because you have only one home page.
4.  Once you have flagged all the pages with `dg-publish` , to publish them, press again `ctrl+p` and from the command menu, choose *Digital Garden: Publish multiple notes*. This command will publish and update all the notes that are flagged with `dg-publish`.

>[!tip]- How to add page properties?
> - Use the **Add fil property** command
> - In *source mode* by adding --- to the top of the page and to below the properties.
> - By using the `ctrl+;` hotkey.
> - By pressing `ctrl+p` to open the command menu and type "Digital Garden: Add publish flag"

 
 > [!tip]- Useful Links
 > [Digital Garden Docs](https://dg-docs.ole.dev/)
 > [Fine Grain Token](https://dg-docs.ole.dev/advanced/fine-grained-access-token/)
 > [Sharaf's Tutorial](https://sharaf.cc/40-49-toolbox/40-note-taking/40-01-obsidian/guides/publish-obsidian-vault-for-free/)
