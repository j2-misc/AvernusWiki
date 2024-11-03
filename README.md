# AVERNUS WIKI
This repository hosts the [AvernusWiki](https://j2-misc.github.io/AvernusWiki/). It was written using [Obsidian](https://obsidian.md/) and the remote website was built using [Quartz 4.0](https://github.com/jackyzha0/quartz), the documentation for which can be found [here](https://quartz.jzhao.xyz/).
# SETUP
Here I'm gonna outline how to get everything set up to contribute to a preexising wiki.
## REQUIREMENTS
In order to contribute to an Obsidian-Quartz Wiki, you'll need a few things:
1. A GitHub account
2. Git installed
3. GitHub CLI installed
4. NodeJS (v20+) and npm (v9.3.1+) installed
5. (optional) it is recommended that you have Obsidian installed as well, but it is not necessary
### GITHUB
In order to set up a GitHub account, go to github.com and click sign up for GitHub. It should be fairly straightforward, don't pay them any money when they ask you to. It's a scam to push their dumbass GenAI bullshit with some other features that you don't need.

Once you're all logged in with GitHub, send me your GitHub username and I'll add you to the repository, so you can actually write stuff instead of just read.
### GIT
Go to https://git-scm.com/downloads and download the release appropriate for your Operating System. Go with all the default options when going through the install wizard. After that's all done, verify your installation by opening up a command prompt or terminal
- On Windows: press the win key to open the start menu and type in command prompt then hit enter
- On Mac: click the Launchpad icon in the Dock, type Terminal in the search field, then click Terminal
- On Linux: ctrl + alt + t

Once you're in the terminal, type in git and hit enter. If it outputs a buncha words then you're good. If it yells at you about an unrecognized command, then something went wrong in the install, likely it's not in your pc's path.

If it works and everything's good, close the terminal window.
### GITHUB CLI
https://cli.github.com/ -> download for your OS, install with the default settings. Open up a new terminal window and type in "gh auth login" then hit enter. Hit enter again to go with GitHub.com, then again to go with HTTPS, and one more time to authenticate git with your GH credentials, and a fourth to log in with a web browser.

Copy the code it gives you by highlighting it and using ctrl+shift+c (not ctrl+c as that will end the program prematurely) and then hit enter to open your web browser. Follow the prompts from there and login, it should be fairly intuitive. Once all that's done, we're good on setting up GitHub stuff for now.
### NODE
Go to https://nodejs.org/en/download/prebuilt-installer and download the installer for your operating system. Should be fairly straight forward, and when it's all installed check to make sure everything's good by opening up a terminal window and typing in "node -v" and hitting enter, and "npm -v" and hitting enter. Both should output something like "v22.11.0" or "v10.9.0" if either shows something else, something's gone wrong.
### (optional) OBSIDIAN
Go to https://obsidian.md/ and download the version for your operating system. That's it, no terminal verification or anything.
## CLONING THE WIKI
Once everything's installed, in a folder of your choice, open git.
- If you can't open git directly into a folder, go to the top of the file explorer you're using, copy the absolute path and then open git wherever. Type in `cd "[path]"` and hit enter to move to the desired directory.
Then type in the following commands in sequence (ignore //comments):
```
//clone the remote repository to your local machine
git clone https://github.com/j2-misc/AvernusWiki.git

//move into local repository
cd AvernusWiki

//install additional dependencies
npm i

//set up quartz
npx quartz create

//this will still yell at you anyways, don't worry it's fine
npm audit fix
```
Finally, if you're using Obsidian, open the folder containing the repository as a vault (this folder should have a bunch of subfolders in it like ".github", ".obsidian", "content", etc). It might ask you about enabling community plugins, make sure to enable them.
# CONTRIBUTION
Here I'm going to outline some procedures for contributing to a quartz wiki.
## EXECUTING COMMANDS
For contribution, it is assumed all commands are executed in a terminal window in the directory housing your local version of the quartz repository. If you can open a terminal directly in the folder, then do that. Else, open a terminal window anywhere and type in `cd "[path]"` and hit enter, where \[path\] is the absolute path to the folder of your local quartz repository. It is important that this path is the path to the folder with all the stuff in it, and not just a folder that has the AvernusWiki folder in it.
## BUILDING AND TESTING
In order to test your changes locally before pushing them to the local wiki, you can use the command `npx quartz build --serve` to view a preview at http://localhost:8080/
## SYNCHRONICITY
Generally, we want to avoid merge conflicts, which happen when there are two slightly different versions of the same file that are both trying to get to the same place at the same time. Best practice to avoid this is just to only work on the wiki when no one else is, and be diligent with syncing the remote repository with your local repository.

Whenever you are about to work on the wiki, send a message in the discord, and run the command `npx quartz sync` to get the latest changes. Once you're done send another message and run `npx quartz sync` again to push your changes to the remote repository.
