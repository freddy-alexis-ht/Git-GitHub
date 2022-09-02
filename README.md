## 1. Project Configuration

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

`git add .` .. to add all the files.
`git reset <file>` .. to unstage the file (won't be added)

**Run the commands**
`git status`
`git add .`  
`git commit -m "Project created, module '01-bases' created and initial commands"`  

- If `git init` is executed again, it doesn't delete the existing commits.

## 2. Other commands

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

`git add 01-bases/README.md`
`git commit -m "01-bases/README.md added"`

Make some changes, commit those changes.  
It only works if the file is already being tracked.
`git commit -am "01-bases/README.md edited"`



