## 1. PROJECT CONFIGURATION AND BASIC COMMANDS

For this course it's necessary to have git version 2.10+

### Local-repo and Remote-repo

- Remote-repo creation, name: Git-GitHub
    - Add a README file
    - Licence: GNU GLP v3
- In the file 'pry-git' open GitBash:
    - `git init` .. Local-repo creation.
    - `git remote add origin https://github.com/freddy-alexis-ht/JavaFX.git` .. Repos linking
    - `git pull origin master` .. Branches sync.


It's possible that on execution of `git init` a message is shown recommending us to change the default branch from 'master' to 'main'.  

So, previous of 'git init', we can configure it with:  
`git config --global init.defaultBranch <name>`  

If the branch is already created, the name can be changed with:  
`git branch -m <name>`  

### Project creation

- Open IntelliJ -> New project -> Java: 1.8
    - Project name: pry-git
    - Project location: ..../pry-git

### Initial Commands

`git --version`  

`git help` .. all the commands (this info can be found in the web)  
`git help commit` .. info about 'commit'.

`:` .. at the end of the page.  
`:q` .. 'quit', leave what we're checking.

When working on a local-repo, the email won't be validated. Every commit will have that email.  
To have a remote-repo in GitHub, Bitbucket or other, to register there we'll need an email that will be validated.  
It's recommendable that the email set in the local-repo is the same set in the remote-repo, for sync.

`git --help config`  
`git config --global user.name="freddy"`  
`git config --global user.email="freddy.alexis.ht@gmail.com`  

To check the configuration:  
`git config --global --list`  

To edit the configuration:
`git config --global -e` .. 'e' to open an Editor  
- ..type 'a' to edit -> make changes -> Type 'Esc' 
 
`:wq!` .. w:write -> q:quit -> !:immediately


### Course project

- The project '01-bases' is given in the course: 
- New module -> Name: 01-bases -> paste the files here

![](images/pry_01-bases_added.png)

**Run the commands**
`git status`
`git add .`  
`git commit -m "Project created, module '01-bases' created and initial commands"`  

- If `git init` is executed again, it doesn't delete the existing commits.

***Recovering a previous commit***

`git checkout -- .` .. reconstruct the project as it is in the last commit.  
Remember that it only cares about the tracked files.  
If a file was created, this command wouldn't erase it, because it would be in 'untracked' state.

***Change branch name: main -> master***

`git branch` .. display the branches.
It's better to work in other branches, not in 'master'.

`git branch -m master main` .. change the branch name from 'master' to 'main'.
This applies only to the current repo.

`git config --global init.defaulBranch main`  
This applies to all repos because it's the global config.  

***Undo the 'git add' command***

`git add README.md` .. now the file is added to the stage by git (ready to be tracked). 
`git reset README.md` .. the file is not staged (untracked).
`git rm --cached README.md` .. another option.

`git add 01-bases/README.md`
`git commit -m "01-bases/README.md added"`

Make some changes, commit those changes.  
It only works if the file or files are already being tracked.
`git commit -am "01-bases/README.md edited"`

`git log`  
Hash .. commit unique identifier.  
HEAD -> main .. the last commit was made in branch 'main'.  
Author .. user configuration.

***Adding files to the stage***

`git add *.html` .. all the .html files.
`git add *.js` .. if they are inside a folder, they won't be found.
`git add js/*.js` .. now it does work.

If a new folder is just created, it won't appear on 'git status'.  
Only if it has a file it will be tracked.  
For these cases, git recommends adding the file `.gitkeep`, it has no content, but it's better than adding a random file.

`git add css/` .. all the files and directories inside 'css/'.

***Alias***

`git status` .. displays a lot of information  .
`git status --short` .. displays the info only in one line.

This alias says: 'git s' is equivalent to 'git status --short'  
`git config --global alias.s "status --short"`  

`git config --global --list` .. to check the global configuration.
`git config --global --edit` .. to edit the global configuration.

![](images/alias.png)

- In the video, the author says he uses this:
> git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

![](images/alias-2.png)

As the alias were set in global mode, it affects all repos.


## 2. ADVANCED COMMANDS

### Working in the module '02-instalaciones'

New file: instalaciones.md  
Add some text.  

`git add . -> git commit -m ".."`  

Make some changes in instalaciones.md  

`git diff` .. if there's only one file, there's no need in specifying a file.
`git diff 02-instalaciones/instalaciones.md` .. a file in specific

But, if `git add 02-instalaciones/instalaciones.md` is applied, when running `git diff 02-instalaciones/instalaciones.md` it will do nothing, because those changes are already in the stage.  

`git diff --staged 02-instalaciones/instalaciones.md` .. it compares differences even if changes are already added to the stage.

Doing this in the Console can be confusing. It's better to use the editor.  







