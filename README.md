# INDEX

[1. PROJECT CONFIGURATION AND BASIC COMMANDS](#1-project-configuration-and-basic-commands)<br>
- [1.1 Local-repo and Remote-repo](#11-local-repo-and-remote-repo) //
[1.2 Project creation](#12-project-creation) //
[1.3 Initial Commands](#13-initial-commands) //
[1.4 Course project](#14-course-project)

[2. ADVANCED COMMANDS](#2-advanced-commands)<br>
- [2.1 Diff and Amend](#21-module-02-instalaciones---diff-and-amend) //
[2.2 Time travel, reset and reflog](#22-module-03-heroes---time-travel-reset-and-reflog) //
[2.3 Change name and delete files 'with' git](#23-module-03-heroes---change-name-and-delete-files-with-git) //
[2.4 Change name and delete files 'without' git](#24-module-03-heroes---change-name-and-delete-files-without-git) //
[2.5 Ignoring files](#25-ignoring-files)

[3. BRANCHES & MERGE](#3-branches--merge)<br>
- [3.1 Fast-forward merge](#31-project-04-merge---fast-forward-merge) //
[3.2 Automatic merge](#32-project-04-merge---automatic-merge) //
[3.3 Manual merge (conflicts)](#33-project-04-merge---manual-merge-conflicts)

[4. TAGS](#4-tags)

[5. GIT STASH - TEMPORAL STORAGE](#5-git-stash---temporal-storage)<br>
- [5.1 Stash](#51-stash) //
[5.2 Stash Avanzado](#52-stash-avanzado)

[6. GIT REBASE - EMERGENCY CHANGES](#6-git-rebase---emergency-changes)<br>
- [6.1 Normal Rebase - Updating a branch](#61-normal-rebase---updating-a-branch) //
[6.2 Rebase Squash - Meld commits](#62-rebase-squash---meld-commits) //
[6.3 Rebase Reword](#63-rebase-reword) //
[6.4 Rebase Edit](#64-rebase-edit)

[7. GITHUB: GIT REMOTE, PUSH, PULL](#7-github-git-remote-push-pull)<br>
- [7.1 GitHub - Push](#71-github---push) //
[7.2 New remote repo](#72-new-remote-repo) //
[7.3 Pushing tags from our local-repo](#73-pushing-tags-from-our-local-repo) //
[7.4 Pull the last changes of the remote-repo](#74-pull-the-last-changes-of-the-remote-repo) //
[7.5 Cloning a remote-repo](#75-cloning-a-remote-repo) //
[7.6 Pushing changes to remote-repo](#76-pushing-changes-to-remote-repo)

[8 GITHUB - BASIC](#8-github---basic)

[9 GITHUB - ADVANCED](#9-github---advanced)<br>
- [9.1 Fork - Clone - Collaborations](#91-fork---clone---collaborations) //
[9.2 Forking - Cloning](#92-forking---cloning) //
[9.3 Pull Request](#93-pull-request) //
[9.4 Updating our forked-repo](#94-updating-our-forked-repo) //
[9.5 Workflow introduction (master-feature)](#95-workflow-introduction-master-feature) //
[9.6 Task: Create a new repo and a Tag](#96-task-create-a-new-repo-and-a-tag) //
[9.7 Feature branch - Workflow via Pull Request](#97-feature-branch---workflow-via-pull-request) //
[9.8 Feature branch - Reviewing partners' job](#98-feature-branch---reviewing-partners-job) //
[9.9 Delete unused branches](#99-delete-unused-branches) //
[9.10 Production branch](#910-production-branch) //
[9.11 Recovering the production branch: br-kitkat](#911-recovering-the-production-branch-br-kitkat) //

[10 GITHUB ISSUES - MILESTONES - CONTRIBUTORS](#10-github-issues---milestones---contributors)<br>
- [10.1 Issues](#101-issues) //
[10.2 Milestone (hito)](#102-milestone-hito) //
[10.3 Adding Contributors](#103-adding-contributors)

[11 WIKIS - PROJECTS - GITHUB PAGES - INSIGHTS](#11-wikis---projects---github-pages---insights)<br>
- [11.1 Wikis](#111-wikis) //
[11.2 Projects](#112-projects) //
[11.3 GitHub Pages - User and Repo](#113-github-pages---user-and-repo) //
[11.4 Insights](#114-insights)

[12 ORGANIZATIONS - TEAMS](#12-organizations---teams)<br>
- [12.1 Organizations](#121-organizations) //
[12.2 Teams](#122-teams)

[13 GIST](#13-gist)<br>
- [13.1 Gist plugins - Personal tokens](#131-gist-plugins---personal-tokens) //
[13.2 All Gists](#132-all-gists)

[14 SSH](#14-ssh) 



---

## 1. PROJECT CONFIGURATION AND BASIC COMMANDS
[Index](#index)

For this course it's necessary to have git version 2.10+

---

### 1.1 Local-repo and Remote-repo

- Remote-repo creation, name: Git-GitHub
  - Add a README file
  - Licence: GNU GLP v3
- In the file 'pry-git' open GitBash:
  - `git init` .. Local-repo creation
  - `git remote add origin https://github.com/freddy-alexis-ht/JavaFX.git` .. Repos linking
  - `git pull origin master` .. master-branches sync.


It's possible that on execution of `git init` a message is shown recommending us to change the default branch from 'master' to 'main'.

So, previous of 'git init', we can configure it with:  
`git config --global init.defaultBranch <name>`

If the branch is already created, the name can be changed with:  
`git branch -m <name>`

---

### 1.2 Project creation
[Index](#index)

- Open IntelliJ -> New project -> Java: 1.8
  - Project name: pry-git
  - Project location: ..../pry-git

---

### 1.3 Initial Commands
[Index](#index)

`git --version`

`git help` .. all the commands (this info can be found in the web)  
`git help commit` .. info about 'commit'.

`:` .. at the end of the page.  
`:q` .. 'quit', leave what we're checking.

When working on a local-repo, the email entered won't be validated. Every commit will have that email, even it it's not correct.  
To have a remote-repo in GitHub, Bitbucket or other, to sign up we'll need an email that will be validated.  
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

---

### 1.4 Course project
[Index](#index)

- The project '01-bases' is given in the course:
- New module -> Name: 01-bases -> paste the files here

![pry_01-bases_added](images/pry_01-bases_added.png)

---

***a)Run the commands***  

`git status`  
`git add .`  
`git commit -m "Project created, module '01-bases' created and initial commands"`

- If `git init` is executed again, it doesn't delete the existing commits.

--- 

***b) Recovering a previous commit***

`git checkout -- .` .. reconstruct the project as it is in the last commit. It affects only 'un-staged' changes.  
Remember that it only cares about the tracked files.  
If a file was created, this command wouldn't erase it, because it would be in 'untracked' state.

---

***c) Change branch name: main -> master***

`git branch` .. display all the local branches.
It's better to work in other branches, not in 'master'.

`git branch -m master main` .. change the branch name from 'master' to 'main'.
This applies only to the current repo.

`git config --global init.defaulBranch main`  
This applies to all repos because it's the global config.

---

***d) Undo the 'git add' command***

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
HEAD -> master .. the last commit that was made in branch 'master'.  
Author .. user configuration.

---

***e) Adding files to the stage***

`git add *.html` .. all the .html files.
`git add *.js` .. if they are inside a folder, they won't be found.
`git add js/*.js` .. now it does work.

If a new folder is just created, it won't appear on 'git status'.  
Only if it has a file it will be tracked.  
For these cases, git recommends adding the file `.gitkeep`, it has no content, but it's better than adding a random file.

`git add css/` .. all the files and directories inside 'css/'.

---

***f) Alias***

`git status` .. displays a lot of information  .
`git status --short` .. displays the info only in one line.

This alias says: 'git s' is equivalent to 'git status --short'  
`git config --global alias.s "status --short"`

`git config --global --list` .. to check the global configuration.
`git config --global --edit` .. to edit the global configuration.

![alias](images/alias.png)

- In the video, the author says he uses this:
> git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

![alias-2](images/alias-2.png)

As the alias were set in global mode, it affects all repos.

---
---

## 2. ADVANCED COMMANDS
[Index](#index)

### 2.1 Module '02-instalaciones' - diff and amend

---
***a) Differences: git diff***

New file: instalaciones.md  
Add some text.

`git add . -> git commit -m ".."`

Make some changes in instalaciones.md

`git diff` .. if there's only one file, there's no need in specifying a file.
`git diff 02-instalaciones/instalaciones.md` .. a file in specific

But, if `git add 02-instalaciones/instalaciones.md` is applied, when running `git diff 02-instalaciones/instalaciones.md` it will do nothing, because those changes are already in the stage.

`git diff --staged 02-instalaciones/instalaciones.md` .. it compares differences even if changes are already added to the stage.

Doing this in the Console can be confusing. It's better to use an IDE.

---

***b) Update last commit message***

Only for the last commit, and if it exists only in Local.
For older commits, 'rebase' should be used.

Commit with a mistaken message:  
`git commit -m "incorrect message`

Rewriting the last commit message:  
`git commit --amend -m "correct message"`

To go to the editor and modify the commit message  
`git commit --amend`

It can be checked with: `git log`

---

***c) Revert commit***

If after a commit we feel we still want to add some other changes, the commit can be reverted.  
The last commit will be deleted, but our changes will remain 'staged'. In other words, no fear.

`git reset --soft HEAD^` .. 'HEAD^' is equivalent to 'HEAD^1', es un commit antes del HEAD (last one).  
If it's need to go to other previous commits: HEAD^2, HEAD^3, but it's not recommendable to go to far.

Check the logs wit 'git log'.

Then add the changes with 'git add .' and write the correct commit.  
`git commit -m "another correct message"`

---

### 2.2 Module '03-heroes' - Time travel, reset and reflog
[Index](#index)

***a) Working with the project***

![module-03-heroes](images/module-03-heroes.png)

Consider these commits were made in different times.  
Take into consideration the folders hierarchy in the git commands.  
`git add 03-heroes/src/README.md`  
`git commit -m "README added"`

- The files will be added and committed one by one.
  - Add the README.md: message: README added
  - Add the misiones.md: message: misiones added
  - Add the heroes.md: message: heroes added
  - Add the ciudades.md: message: ciudades added
  - Add the historia.md: message: historia folder added

At this point, we notice that 'historia' folder has two files in it.  
`git commit --amend` .. displays info about the last commit.
- For example, in 'Changes to be commited' we can see that there are two files in the folder 'history'.
- So, it would be better to change the commit-message.

![amend](images/amend.png)

To change the *commit-message*:
- Click 'A' to edit -> Edit -> Esc -> :wq!

![amend-2](images/amend-2.png)

Then, we can see the changes in the log:

![after-amend](images/after-amend.png)

Last commit of this part.
- In 'heroes.md' add the line: 'Linterna verde'.

`git add 03-heroes/src/heroes.md`  
`git commit -m "heroes.md: linterna verde added`

![after-amend-2](images/after-amend-2.png)

---

***b) Using: reset --soft (1 position)***

In heroes.md 'Robin' should've been added too.  
So, reverting the last commit (going back 1 position):  
`git reset --soft HEAD^`  
or  
`git reset --soft HEAD^1`  
or, using the hash:  
`git reset --soft 8c8084c`

In 'heroes.md' write: * Robin  
On `git status`  
.. there'll be two M's (M:modified / green and red)
- Green M: the 'git add' command about 'Linterna verde' entry.
- Red M: the unstaged modification about 'Robin' entry.

![modification-1](images/modification-1.png)

Next, execute the commands:  
`git add 03-heroes/src/heroes.md`  
`git commit -m "heroes.md: heroes Linterna verde and Robin added"`

Check with: `git log`

---

***c) Using: reset --mixed --hard***

- --soft: keep the files and the stages (the 'git add' command, meaning: they are in green)
- --mixed: keep the files, but unstage changes (it doesn't only revert 'commit' but 'add' also)
- --hard: destroy the files and any changes made.

![modification-2](images/modification-2.png)

For some reason it's necessary to go back to the commit 'ciudades added' (hash: bacc4ca)  
  `git reset --mixed 2533abc`  (default: --mixed)

- Files are still there, but changes are unstaged. ('commit' and 'add' reverted)

Having seen that we don't need those changes, they can be discarded:  
`git reset --hard 2533abc`  
The files deleted can be recovered, but this will be seen later.

![modification-3](images/modification-3.png)

Note that even when the commit related to 'historia' folder has been reset, it's still there. The files are not tracked.

![modification-4](images/modification-4.png)

---

***d) Reverting the reset***

We realized that the deleted commits were ok, and we want to undo all the resets (soft, mixed, hard).  
We want to go back to were 'Linterna verde' and 'Robin' were added (hash: ea4bf49).    
Each 'hash' represents modifications in the history of logs.

`git reflog`

![modification-5](images/modification-5.png)

- Note that currently we're now in the 'HEAD@{0}', right after we run 'git reset --hard'.
  - 'HEAD@{0}' is the 'git reset --hard'.
  - 'HEAD@{1}' is the 'git reset --mixed'.
  - 'HEAD@{3}' is the 'git reset --soft'.


- Going back to the hash: ea4bf49  
  `git reset --hard ea4bf49`  
  `git log`

![modification-6](images/modification-6.png)

- These operations shouldn't be done freely because they might be dangerous.
- It's better to create a branch, work there, and once we're sure our changes are correct, merge our branch with the 'master' one.

---

### 2.3 Module '03-heroes' - change name and delete files with git
[Index](#index)

***a) Renaming***

In '03-heroes/src/' create the file 'destroy.md' and add some text.
- This file contains info to destroy the world.  
  `git add 03-heroes/src/destroy.md`  
  `git commit -m "destroy.md added"`  
  `git log`

But, what about if it was a mistake, the file should be called 'save.md' and it should contain info to save the world.
- To restore this, we could use the 'reset' commands.
- Notice that if 'reset' is applied, then the commit will be reverted, and in future logs the last commit won't be displayed.


If I want to keep the commit in the logs, and I want to change the file name and its info:
>mv: move, if it moves in the same place it renames the file

`git mv 03-heroes/src/destroy.md 03-heroes/src/save.md`

The file-name now is 'save.md'. It can be seen with:
test
`git status`

![rename](images/rename.png)

We have what we wanted, everything in the logs.

![rename-2](images/rename-2.png)

---

***b) Deleting***

`git rm 03-heroes/src/save.md`  
When the file is deleted, it's still in the stage (to be committed).
- It can be brought back with:  
  `git reset --hard`  
  `git checkout -- .`

![delete](images/delete.png)

So, we go again:  
`git rm 03-heroes/src/save.md`  
`git status`  
`git commit -m "save.md deleted"`

![delete-2](images/delete-2.png)

`git log`    
We have what we wanted, everything in the logs.

![delete-3](images/delete-3.png)

---

### 2.4 Module '03-heroes' - change name and delete files without git
[Index](#index)

***a) Renaming***

We have:
- historia (directory)
  - batman.historia.md (file)
  - superman.historia.md (file)

Those files are inside 'historia', so having 'historia' in their names is repetitive.
- Right click -> Refactor -> Rename -> superman.md

In the image, git recognizes the action of rename.

![rename-3](images/rename-3.png)

> In the video, it's different, maybe because of the git version.  
> There, after 'git status' it was like:
> -  D historia/superman.historia.md
> - ?? historia/superman.md
>
> Meaning that, it consider that the original file was deleted, and a new one was created.

> After executing 'git add .' and 'git status', it was like this:
> - R historia/superman.historia.md -> historia/superman.md
>
> At this point, git recognized that both files are the same, it just was renamed.
> And that's exactly what git did in my case.

`git commit -m "superman.historia.md renamed to superman.md"`  

If we go back 1 commit with:  
`git reset --hard db39a6d`  
We'll see how git sets back the name to 'superman.historia.md'.  

And, executing:  
`git reflog`
`git reset --hard 91964ea`  
We go back to the last commit, when the name was 'superman.md'.  

---

***b) Deleting***  

Differences:
- Deleting via git: it keeps the file as staged (git add applied).
- Deleting via IDE (manual): the file is un-staged (has to apply git add).

---

### 2.5 Ignoring files
[Index](#index)

Create some files that we don't want to be tracked.  
`git status`  
![ignore-1](images/ignore-1.png)

Create the file '.gitignore'. It should be tracked, because we might add some more files we don't want to track.  
The first one is for directories, and the next one for files.  
> dont-track-this/  
> dont-track-me.md

`git status` .. it only displays the .gitignore.  

---
---

## 3. BRANCHES & MERGE
[Index](#index)

***a) Merge types***

- Fast-forward: There are no changes in the master-branch, so the changes in the other-branch can be merged easily. Each commit will be part of the master-branch, just like if the other-branch wouldn't have been created.  
- Automatic merge: There were changes in the master-branch, but there are no conflicts with what's been changed in the other-branch.
- Manual merge: In both branches the same code was modified, git will ask us to solve it manually. After the problem is solved, git creates the 'merge-commit' and we can continue.

![fast-forward-merge](images/fast-forward-merge.png)
![merge-conflict](images/merge-conflict.png)

---

### 3.1 Project '04-merge' - Fast-forward merge
[Index](#index)

***a) Project***

- The project '04-merge' is included in the course.  

![pry-04-merge](images/pry-04-merge.png)

- It already has a .git, which means it already has a history.

![merge-1](images/merge-1.png)

---

***b) Working with the branch***

While being in 'master' create the file 'villanos.md', add some code.  
In the image, the first status displays villanos.md and a directory that I included in the .gitignore.  
I added that in the .gitignore. That's why now the .gitignore is displayed with the 'M' of 'modified'.  

`git branch br-villanos` .. to create a branch.  
`git branch` .. to see the current branch and the rest of them.  
`git checkout br-villanos` .. to jump to another branch.  

In the logs, we can see that the last commit for both branches is the 'Agregando el gitignore'.  

![merge-2](images/merge-2.png)

Being in the br-villanos branch, run these commands:  
`git add .`  
`git commit -m "..."`  
`git log`

In the logs we can see that 'master' is 1 commit behind 'br-villanos'  

![merge-3](images/merge-3.png)

Still in 'br-villanos' edit the 'villanos-md' file.
`git commit -am "..."`  
`git log`

In the logs we can see that 'master' is 2 commits behind 'br-villanos'

![merge-4](images/merge-4.png)

---

***c) Merging***

If we go back to 'master' the 'villanos.md' file won't be there.  
Maybe that file is ready to pass to the 'master', this is how it's done.  

> To merge changes in branch-A to branch-B, we have to in branch-B.

So, to merge changes from 'villanos.md' to 'master', we have to be in 'master'.  

`git checkout master`  
`git merge br-villanos`  
`git log`  

In the image, it says that it was 'Fast-forward' merge, meaning that there was no conflict.  
We also can see that both branches are on the same level now.  

![merge-5](images/merge-5.png)

After a successful merge, the 'br-villanos' branch should be deleted.  

`git branch -d br-villanos`  

If there are some changes that haven't been committed, git will warn us about that.  
If we don't mind about those changes, to force the deletion we can use: 

`git branch -d br-villanos -f`

---

### 3.2 Project '04-merge' - Automatic merge
[Index](#index)

To create a branch and to move to it:  
`git branch br-villanos`  
`git checkout br-villanos`  

It can be done in one step:  
`git checkout -b br-villanos`  

Being in 'br-villanos' branch, in 'villanos.md' add the last line (4.).  

~~~
## Villanos

1. Lex Luthor
2. Joker
3. Flash Reverso
4. Doomsday
~~~

`git commit -am "Doomsday added"`

After the commit I add another line to 'villanos.md', it can be seen with 'git status'.  

![automatic-merge-1](images/automatic-merge-1.png)

`git commit -am "Notes added"`

On 'git log' we'll see that 'master' is 2 commits behind.  

Suddenly, we are asked to change something, but as the 'br-villanos' is not ready to be merged and the request is urgent, the changes are made in 'master'.  

`git checkout master`  

In 'heroes.md' delete 'Daredevil'.  

`git commit -am "Daredevil deleted"`

Now, we know that 'master' has its own commits in its timeline.  
Also, 'br-villanos' has its own commits in its timeline.  

> In this part I'll use this alias:
> git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

`git lg`  

![automatic-merge-2](images/automatic-merge-2.png)

It's time to merge both branches.  

`git merge br-villanos`  

It will display:

![automatic-merge-3](images/automatic-merge-3.png)

- In the editor: Click 'A' to edit -> change the message to "Merge 'master with branch 'br-villanos'" -> Esc -> :wq!

![automatic-merge-4](images/automatic-merge-4.png)  
![automatic-merge-5](images/automatic-merge-5.png)  

- If the modified files are text, and if they are modified in different places, then git will use this strategy ('ort', formerly known as 'recursive')  
- But if the files are binaries, like images, even if they are not modified in the same place, git will consider that there is conflict.  

**To avoid confusions**  

1. The three commits are merged:
  - So, Daredevil will be deleted and Doomsday and notes will be added. This is how the 'master' will end.
  - Don't confuse, the 'br-villanos' branch will continue with its 2 commits, Doomsday and notes are added, and Daredevil will be there, because it wasn't affected in this timeline.  
~~~
    ?? 6f850f5 - (4 minutes ago) Merge 'master with branch 'br-villanos' - Freddy2 (HEAD -> master)  
    |\  
    | ?? 6ed8522 - (18 minutes ago) Notes added - Freddy2 (br-villanos)  
    | ?? e0e9975 - (22 minutes ago) Doomsday added - Freddy2  
    ?? | 238ae61 - (14 minutes ago) Daredevil deleted - Freddy2  
    |/  
    ?? 2cbcce8 - (74 minutes ago) Flash reverso added - Freddy2  
~~~

---

### 3.3 Project '04-merge' - Manual merge (conflicts)  
[Index](#index)

Both branches modified the same file.

`git checkout -b br-conflicto`  
Edit 'misiones.md'.  
`git commit -am "misiones.md updated"`  

`git checkout master`  
Edit 'misiones.md'.  
`git commit -am "misiones.md updated in master"`  

`git merge br-conflicto`  
> Auto-merging misiones.md  
> CONFLICT (content): Merge conflict in misiones.md  
> Automatic merge failed; fix conflicts and then commit the result.  

- The files that didn't have conflicts will be merged.  
- After fixing the conflict, another commit should be run.

IntelliJ display the conflict like this:  
- From line 1 to 4 both have the same content.
- HEAD refers to the last commit, in this case it was in 'master'.  
  - Between HEAD and ===, are displayed the differences.
- br-conflicto is the other branch.  
  - Between === and br-conflito, are displayed the differences.

![conflict-1](images/conflict-1.png)

Read the conflict and solve it manually. Then commit.  

`git commit -am "Conflict solved"`  

![conflict-2](images/conflict-2.png)

Delete the other branch.  

---
---

## 4. TAGS
[Index](#index)

Reference to a specific commit and to the state of a project in a period of time.  

![tag-1](images/tag-1.png)

Considering that in the last commit our app is ready to be uploaded to a production-server.  
So, it could be marked with a release-tag.  
It creates a tag exactly in the last commit.  

`git tag my-release`  

![tag-2](images/tag-2.png)

`git tag` .. to see all tags.  
`git tag -d my-release` .. to delete a tag.  

The tag should be informative, usually with numbers.  

![tag-3](images/tag-3.png)

v1.0.0 -> [major-change].[new-functionality].[bug-fix]

To create a tag in the last commit, it's not necessary to write the hash or HEAD^.  
To create a tag in any commit .. copy the hash:  

`git tag -a v0.1.0 2cbcce8 -m "Version: alpha"`  

![tag-4](images/tag-4.png)

Tag description:

`git show v0.1.0`  

![tag-5](images/tag-5.png)

---
---

## 5. GIT STASH - TEMPORAL STORAGE
[Index](#index)

***Stash***  
It's like a vault where we can put files, even those untracked by git.  

Scenario:
- We're working on a branch, it can be 'master' or other branch.  
- We're asked to go to the last commit, but we don't want to commit the changes we have so far.
- We save those un-committed changes with Stash.
- We go to the last commit and do what we have to, then we can recovery our progress from the stash.  

This action can cause scenarios just like the ones we saw with 'merge'.  
**Tip:** It's better to save only one stash and attend to it as soon as possible. Having many stashes can be confusing.  

***Rebase***  
It allows to join/split commits, to rename commits, ...  
**Tip:** Use it only if we haven't merged our changes to other repo. Also, don't change the History, because maybe they were already merged to a main repo.  

---

### 5.1 Stash   
[Index](#index)

This project will be used for this part:  

![demo-stash](images/demo-stash.png)

This is the current log:  

![current-history](images/current-history.png)

***a) Stash without conflicts***

In the 'master' branch.  
The file 'misiones.md' is like this:  
~~~
# Misiones

1. Acabar con el plan de Lex Luthor
2. Crear la liga de la justicia
3. Buscar nuevos miembros para la liga
4. Necesitamos m??s comida
~~~

Then, we add an extra line (not commit):  
~~~
5. Hacer un reconocimiento del terreno
~~~

Suddenly, we are asked to deploy the 'master' branch to Production.  
But, there are some changes we are not ready to merge to 'master' (if we weren't working in master, the stash wouldn't be necessary here).  
  - If we were in branch-1, and we're asked to deploy master, we'd just have to switch to master and deploy it.  
  - Nevertheless, we have to undo our changes without losing them.  

`git stash`  
After the command, we can see our changes are not there anymore, we went back to the last commit.  
When executing 'git status' it'll say 'nothing to commit'.  
WIP: Work In Progress.  

![stash-1](images/stash-1.png)

`git stash list`  
> stash@{0}: WIP on master: 5440fe5 Resolviendo conflictos

**Doing some more changes in master**  

The file 'README.md' initially it's like this:  
~~~
# Motivo

Este repositorio sirve para probar cosas
~~~

We change it to this:  
~~~
# Notas

Este es un repositorio de los h??roes.
~~~

`git commit -am "README added"`  
`git lg`  

The stash is there, but git will continue working as if it weren't. It's us who should track stashes, remember that we created them.  

![stash-2](images/stash-2.png)

**Recovering our work from stash**   

Obviously, we know that changes were made in different locations, so there shouldn't be conflict.  

`git stash pop`  
Recoveries our changes.  
Keeps the last commit.  

In the image, we can see that 'git stash pop' displays a similar message as with 'git status'.  
We also can see that the 'stash@{0}' was dropped. Meaning that, if we'd have had 2 stashes: 'stash@{0}', 'stash@{1}', the first one was dropped, and 'stash@{1}' now is 'stash@{0}' (the only stash that exists).    

![stash-3](images/stash-3.png)

To finish, the commit:  
`git commit -am "misiones.md updated"`

---

***b) Stash with conflicts: Auto-merging***

**Working in the same file, but not the same line**  

Before:  
~~~
# Notas

Este es un repositorio de los h??roes.
~~~

After:  
~~~
# Notas

Este es un repositorio de los h??roes.
Texto agregado.
~~~

`git stash`  
Now we're in the last commit, and make changes over the same file we have an stash.  

~~~
# Objetivos

Este es un repositorio de los h??roes.
~~~

`git commit -am "README updated with 'objetivos'"`  
`git lg`

Popping the stash:  
As there was no real conflict, this command works the same way as in the previous example.  
`git stash pop`  
`git lg`  

![stash-4](images/stash-4.png)

~~~
# Objetivos

Este es un repositorio de los h??roes.
Texto agregado.
~~~

---

***c) Stash with conflicts: Auto-merging***

**Working in the same file, and in the same line**  

Before (master-branch):  
~~~
# Objetivos

Este es un repositorio de los h??roes.
Texto agregado.
~~~

After (master-branch):
~~~
# Objetivos del repositorio

Este es un repositorio de los h??roes.
Texto agregado.
~~~

`git stash`  
The code goes back to this:  
~~~
# Objetivos

Este es un repositorio de los h??roes.
Texto agregado.
~~~

Then (master-branch), a change and a commit:  
~~~
# Objetivos del repositorio principal

Este es un repositorio de los h??roes.
~~~

`git commit -am "README updated first line"`  
`git stash pop`  

There is conflict, the stash is not dropped.  

![stash-5](images/stash-5.png)  
![stash-6](images/stash-6.png)  

We have to solve the conflict. In the end, we'll keep the file like this.  

~~~
# Objetivos y Notas

Este es un repositorio de los h??roes.
Texto agregado.
~~~

`git commit -am "stash conflict solved"`  

Remember the stash wasn't dropped.  
`git stash list`  

---

### 5.2 Stash Avanzado  
[Index](#index)

`git stash clear` .. removes all the stashes.  
- They can be recovered with 'git reflog'.  

***a) Many stashes in the same line***

In 'villanos.md' add a 5th line creating 3 stashes.  
As we can see, the command 'git stash list' doesn't say much.  
We only know that 'stash@{0}' is the last stash added.

![stash-7](images/stash-7.png)

This command recoveries a specific stash, but doesn't drop the stash:    
`git stash apply stash@{2}`

To delete a specific stash (both are the same):  
`git stash drop`  
`git stash drop stash@{0}`  

The list of stashes don't display enough info.  
This commands displays more info:  
`git stash show stash@{1}`  

~~~
$ git stash show stash@{1}
 villanos.md | 1 +
 1 file changed, 1 insertion(+)
~~~

**It's better to assign a name to the stash**

`git stash save "Added Rinox in villanos.md"`

~~~
$ git stash list
stash@{0}: On master: Added Rinox in villanos.md
stash@{1}: WIP on master: afacf02 stash conflict solved
stash@{2}: WIP on master: afacf02 stash conflict solved
stash@{3}: WIP on master: afacf02 stash conflict solved
~~~

**To display more info about the stash**

`git stash list --stat`

![stash-8](images/stash-8.png)  

**Choosing only 1 stash**  

So far I have 4 stashes, let's say I decided to keep only the last one.  
`git stash pop`  
`git commit -am "Rinox added to villanos.md"`  
`git stash clear`  

***More info about stash: https://git-scm.com/docs/git-stash***

---
---

## 6. GIT REBASE - EMERGENCY CHANGES
[Index](#index)

***Simple Rebase***  

There are two branches: master and feature.  
The last commit in common of these branches is 'Old Base'.  
Eventually, 'feature' committed some changes, also 'master' did.  
However, those commits in 'master' are necessary in 'feature'.  
In cases like this, 'git rebase' is applied.  

![rebase-1](images/rebase-1.png)

***Interactive Rebase***  

`git rebase -i HEAD~3`  
It moves the last 3 commits to a Temporal-Area, and later they are put back in the same order.  

4 Use cases:  
- Order commits.
- Correct commit messages.
- Join commits.
- Split commits.  

---

### 6.1 Normal Rebase - Updating a branch
[Index](#index)

In this part this project will be used:  

![rebase-2](images/rebase-2.png)

In the image, the last commit in common is 'acea380: Actualizaci??n de las misiones'.  
Then, both branches have 2 commits.  
The branch 'rama-misiones-completadas' haven't been merged to the 'master'. 

Task: the branch 'rama-misiones-completadas' must have the 2 commits in 'master' as if they were part of 'rama-misiones-completadas'.  

~~~
--> ace -> 300 -> 158    (master)
          \  
           cc5 -> 8e7     (rama-misiones-completadas)
~~~  

![rebase-3](images/rebase-3.png)

- Change to branch 'rama-misiones-completadas'.  
`git checkout rama-misiones-completadas`  
`git rebase master`  
`git lg`  

Note that the hashes: cc5, 8e7 from 'rama-misiones-completadas' are not in the logs anymore, they've been replaced by other hashes.  
But, now the branch 'rama-misiones...' has the two commits of 'master'.  

~~~
                     (rama-misiones-completadas)
                                 |
--> ace -> 300 -> 158 -> 141 -> 9ec 
                   |   
                (master)
~~~

![rebase-4](images/rebase-4.png)

The branch 'rama-misiones-completadas' is 2 commits ahead of 'master', and the 'master' has no extra commits. So, when merging it will be a 'fast-forward' merge.  
Move to 'master' and merge.

`git checkout master`  
`git merge rama-misiones-completadas`  

![rebase-5](images/rebase-5.png)

The branch 'rama-misiones-completadas' can be deleted.  
`git branch -d rama-misiones-completadas`  

> This is one way 'rebase' can be used.  
> However, sometimes is better to use 'merge' in order to solve conflicts.  

---

### 6.2 Rebase Squash - Meld commits
[Index](#index)

Being in 'master'.  
There are two files: misiones.md & misiones-completadas.md  

Before:
~~~
misiones.md
# Misiones

1. Acabar con el plan de Lex Luthor
2. Crear la liga de la justicia
3. Buscar nuevos miembros para la liga
5. Investigar los trabajos del Joker
6. Tratar de investigar que trama el Flash Reverso
~~~

~~~
misiones-completadas.md
# Misiones

* Crear la liga de la justicia
* Investigar los trabajos del Joker
~~~

After: Let's say the mission 6 has finished, so it should be in 'misiones-completadas.md'.  
~~~
misiones.md
# Misiones

1. Acabar con el plan de Lex Luthor
2. Crear la liga de la justicia
3. Buscar nuevos miembros para la liga
5. Investigar los trabajos del Joker
~~~

~~~
misiones-completadas.md
# Misiones

* Crear la liga de la justicia
* Investigar los trabajos del Joker
* Tratar de investigar que trama el Flash Reverso
~~~

Run the commands:  
`git status`  
`git commit -am "Actualizamos misiones completadas`  
`git lg`  

![rebase-6](images/rebase-6.png)

As we can see in the image, the last 2 commits are kind of the same. So, they should be only one.  
Have in mind that, 'rebase' (rename, join, split) should be used when working in local, and only when necessary.  

**Join commits**

Being in 'master'.  
`git rebase -i HEAD~4`  

In the image, there are a lot of options. Among all of those, the one we care is 'squash'.  
- pick (p) is to 'use' a commit.  
- squash (s) is to 'meld' the commit with the previous one.

![rebase-7](images/rebase-7.png)

So, click 'A' (to edit) -> after edit -> Esc -> :wq!  

~~~
pick 158ba9e Se agrego a la liga: Volc??n Negro
pick 141071a Agregamos el archivo de las misiones completadas
pick 9ecb331 Actualizamos dos misiones completadas al momento
squash c731cc5 Actualizamos misiones completadas
~~~

Then, we'll have:  
Just: :wq!

![rebase-8](images/rebase-8.png)  

It will display:  
~~~
$ git rebase -i HEAD~4
[detached HEAD 4048dd5] Actualizamos dos misiones completadas al momento
 Author: Strider <fernando.herrera85@gmail.com>
 Date: Fri Jun 23 15:44:41 2017 -0600
 2 files changed, 4 insertions(+), 1 deletion(-)
Successfully rebased and updated refs/heads/master.
~~~

The log initially was:  
~~~
$ git lg
* c731cc5 - (3 seconds ago) Actualizamos misiones completadas - Freddy2 (HEAD -> master)
* 9ecb331 - (5 years ago) Actualizamos dos misiones completadas al momento - Strider
* 141071a - (5 years ago) Agregamos el archivo de las misiones completadas - Strider
~~~

After rebase-squash is:  
~~~
$ git lg
* 4048dd5 - (5 years ago) Actualizamos dos misiones completadas al momento - Strider (HEAD -> master)
* 141071a - (5 years ago) Agregamos el archivo de las misiones completadas - Strider
~~~

The last commit (3 seconds ago) meld with the previous one (5 years ago). Check the files.  

**Note**  
It can be 'p' or 'pick', and 's' or 'squash'.  
If we had wanted to meld the 3 last commits then it should have been like this:  
~~~
pick 158ba9e Se agrego a la liga: Volc??n Negro
p 141071a Agregamos el archivo de las misiones completadas
s 9ecb331 Actualizamos dos misiones completadas al momento
s c731cc5 Actualizamos misiones completadas
~~~

---

### 6.3 Rebase Reword
[Index](#index)

`git rebase -i HEAD~4`  

Interactive window:
~~~
pick 300c014 Misiones nuevas agregadas
pick 158ba9e Se agrego a la liga: Volc??n Negro
pick 141071a Agregamos el archivo de las misiones completadas
pick 4048dd5 Actualizamos dos misiones completadas al momento

# Rebase acea380..4048dd5 onto acea380 (4 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
~~~

To change the messages in the last 2 commits 'reword'.  

~~~
pick 300c014 Misiones nuevas agregadas
pick 158ba9e Se agrego a la liga: Volc??n Negro
reword 141071a Agregamos el archivo de las misiones completadas
reword 4048dd5 Actualizamos dos misiones completadas al momento
~~~

It will take us to another interactive window:  

![reword-1](images/reword-1.png)

This is the message of the last-commit.  
Change the message from:  
- Agregamos el archivo de las misiones completadas   
To:  
- misiones-completadas.md added   
Esc -> :wq!  

Then, we go for the other commit message.  
Change the message from:  
- Actualizamos dos misiones completadas al momento  
To:
- misiones.md updated  
Esc -> :wq!  

Check the logs:  
![reword-2](images/reword-2.png)

---

### 6.4 Rebase Edit
[Index](#index)

Modify the files: README.md, misiones.md, villanos.md.  
Then, we decide to revert what was done in README.md.  
`git checkout -- README.md`  

![edit-1](images/edit-1.png)  

Commit the changes in the files.  

![edit-2](images/edit-2.png)  

But, then we decide that each file should have its own commit.  
- We could reset the last commit.
- Or, use the interactive rebase.

`git rebase -i HEAD~3`  

Before:  
~~~
pick ff800e4 misiones-completadas.md added
pick 5a9f6f6 misiones.md updated
pick da8e603 commits
~~~

After:  
~~~
pick ff800e4 misiones-completadas.md added
pick 5a9f6f6 misiones.md updated
edit da8e603 commits
~~~
Esc -> :wq!  
Then, we're back.  

`git status`  
`git reset HEAD^`  

![edit-3](images/edit-3.png)

In this point, we're right before we 'add' the changes in the two files.  

`git add villanos.md`  
`git commit -m "villanos.md updated"`  

`git add misiones.md`  
`git commit -m "misiones.md updated"`  

![edit-4](images/edit-4.png)

But, it hasn't finished.
With 'git status' we can notice that we still in 'interactive rebase in progress'.  
Run:
`git rebase --continue`  
There are no more tasks, so this will end the 'interactive rebase'.  

![edit-5](images/edit-5.png)

---
---

## 7. GITHUB: GIT REMOTE, PUSH, PULL
[Index](#index)

- Have in mind that Git doesn't manage access control to the repo. For this task we have some 'hosted services' like: 
  - GitHub, Bitbucket, ...
- And, managed by ourselves like: 
  - Gitosis is a tool which provides access control and remote management for hosted Git repositories. It allows for fine-grained management of read and write access over SSH, without requiring that the users have local system accounts on the server.  

Gitosis oficial links:
- [What is Gitosis?](https://wiki.archlinux.org/title/gitosis#:~:text=Gitosis%20is%20a%20tool%20which,system%20accounts%20on%20the%20server.)
- [Install and configure](https://github.com/res0nat0r/gitosis)

Useful link:
- [Save user and pass of GitHub](https://docs.github.com/es/get-started/getting-started-with-git/caching-your-github-credentials-in-git#platform-windows)

---

### 7.1 GitHub - Push
[Index](#index)

'origin' is the name of the repo, it's a convention.  
`git remote add origin [URL]`  

99% of times the 'fetch' and 'push' will be the same repos (URL). 
- 'fetch' is the place from where we get data.
- 'push' is the place where we send data.  
Here we see that the word/name 'origin' is associated to that URL.  

`git remote -v`  
~~~
origin  https://github.com/freddy-alexis-ht/Git-GitHub.git (fetch)
origin  https://github.com/freddy-alexis-ht/Git-GitHub.git (push)
~~~

`git push -u origin master`  
'origin' is the name of the remote repo.  
'master' is the local branch we want to push.  
'-u' sets 'master' by default, so in the next time it will be enough 'git push'.  

---

### 7.2 New remote repo
[Index](#index)

***Local repo***

![remote-1](images/remote-1.png)  

***Remote repo***

GitHub -> New repo -> Name: git-course -> Public  
Copy the URL: https://github.com/freddy-alexis-ht/git-course.git  

On GitBash, run the commands:  
`git remote add origin [URL]`  
`git push -u origin master`  

![remote-2](images/remote-2.png)  

---

### 7.3 Pushing tags from our local-repo
[Index](#index)

***a) Tags***

In the remote-repo interface we'll see '0 tags'.  
But, in the local-repo there are tags.  
~~~
$ git tag
v0.1.0
v1.0.0
v2.0.0
~~~

Manually we have to push them.  
`git push --tags`

![remote-3](images/remote-3.png)  

Refresh the remote-repo. Click in it.   
This is the command that was used to create the first tag.    
`git tag -a v2.0.0 c3e22b9 -m "Version 2.0.0 Deadshot"`  

In the image we can see the date, the hash (commit), options to download.
A tag is useful because there is a URL that can take us to it:
- https://github.com/freddy-alexis-ht/git-course/releases/tag/v2.0.0

![remote-4](images/remote-4.png)  

It's possible to download clicking in 'zip'.
- Downloading we'll get the project without the .git (the History won't be downloaded).  
- Cloning the repo, we'll get .git too.  

Clicking in the hash (c3e22b9) will take us to the image.  
It shows the differences: before commit / after commit.  

![remote-5](images/remote-5.png)  

If the mouse is over a line, a blue + appears. Click in it, we'll be able to leave a comment.  
Writing ':' will display emojis.  

***b) Releases***

In the remote-repo -> right panel there are three options:
- Releases / 3 tags / Create a new release.

Click in 'Releases'
- It displays the message "There aren't any releases here".  

In that same place click in 'Tags'.  
- Click in 'v2.0.0' -> Create release from tag.  
- Add the description using MarkDown.  
- It's possible to add binaries (images, ...).

![remote-6](images/remote-6.png)  

After it, now in 'Releases', there will be one.

![remote-7](images/remote-7.png)  

And, in the main-page of the remote-repo, the Release will be there.

![remote-8](images/remote-8.png)  

---

### 7.4 Pull the last changes of the remote-repo
[Index](#index)

It's possible to edit a file in GitHub.  
- README.md -> Edit
- Commit message ..
- Commit directly to the 'master' branch.
- Commit changes

In the local-repo we don't have that edition.  
As we executed previously the command:  
`git push -u origin master`  

It's enough to use the command:  
`git pull`  
..equivalent to:  
`git pull origin master`  
..the 'origin' can be verified with:  
`git remote -v`

As we can see in the image, it applied the 'fast-forward' because there were no conflicts.  

![pull-1](images/pull-1.png)

-> To check, whether the local-repo is different from the remote-repo:  
`git remote update`  
`git status -uno`  

![pull-2](images/pull-2.png)

---

### 7.5 Cloning a remote-repo
[Index](#index)

Delete the project '09-heroes' .. this is to simulate that we lose our work.  
There's no problem, because it's in GitHub.  

GitHub -> Code (Clone) -> HTTPS -> Copy the URL.  
`git clone [URL]`  

Note the repo is cloned with the name as it's in the remote: git-course.  

![clone-1](images/clone-1.png)

---

### 7.6 Pushing changes to remote-repo
[Index](#index)

`git status`  
`git add .`  
`git commit -m "README.md updated again"`  

With 'git lg' we can see that the local-repo is 1 commit ahead the origin (remote-repo).  

`git push`

***Generating a conflict***

In remote-repo edit README.md and commit.   
In local-repo edit README.md and commit.   

Pulling in the local-repo.  
`git pull`  
~~~
From https://github.com/freddy-alexis-ht/git-course
   199b7f0..5f3724d  master     -> origin/master
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
~~~

If we check the IDE:

![pull-3](images/pull-3.png)

Remember at this point we're not in a specific branch, we're in rebase.
Solve the conflict, edit the README.md in the IDE.  

Save changes in local-repo.  
`git add .`  
`git commit -m "README.md modificado"`  

Now, it should be pushed to remote-repo.    
`git push`  

There are some configurations we can apply, but it wasn't necessary for me.  
~~~
git config --global pull.ff only  
git config --global pull.rebase true  
~~~

---
---

## 8 GITHUB - BASIC
[Index](#index)

***a) GitHub Interface***

For example, if we check 'React' account:
- Star .. it's like a 'Like'.
- Watch .. it's like a 'Follow'. It's to be notified of activities and changes.  

Tabs:
- Code: The repo and its branches.  
- Issues: Problems, suggestions, bug-fixes found and reported in our repo. They will be 'Open', and after it's solved, it'll be 'Closed'.  
- Pull requests: To make changes to someone's repo, after validation.
- Projects: Organize the project status, plan its future.  
- Wiki: Official Documentation.  
- Security: The teamwork that attends: deprecated libraries, legacy code, vulnerabilities, ...  
- Insights: Statistics, the workflow of our team in the repo: contributors, community, commits, code frequency, ...
- Fork: Copy a repo to my GitHub account, there it can be edited the way we want.

---

***b) MarkDown***

Links:  
- [GitHub Docs](https://docs.github.com/es)
- [Emojis](https://www.webfx.com/tools/emoji-cheat-sheet/)
- [MarkDown Tutorial](https://www.markdowntutorial.com/)

---

***c) Search file: Go to file***

The 'Go to file' button take us to the image:  
![search-1](images/search-1.png)

When clicking on that particular file, there are three other options:
- Go to line: To go to a specific line (when it's code or text).
- Copy path: It would copy: 'historia/superman.md'. 
- Copy permalink: It creates a link that takes us exactly to that file.

--

***d) Raw, Blame, History, Edit, Delete***

- Raw: Opens a window with the file in a .txt format. It's possible to copy the link, and it will take us exactly to that raw view.
- Blame: It's to know who did what and when. It shows the changes in a file since it was created, we can travel through commits.
  - History: Timeline of commits.
  - Normal view: To leave the 'Blame view'.
- Edit: Icon: 'pencil'.
- Delete: Icon: 'trash'.
  - After click, it requires to do a commit.

---

***e) Create a new file in GitHub***

Pull request: If we want to merge the branch-A with master. A pull-request will be useful to analyze the changes, this will be done by someone with higher skills.  
This is usually done from the local-repo, but it's possible from the remote-repo too.

- GitHub -> 'historia' folder -> Add file: Create new file -> batman.md (add some text)  
- Commit message: batman.md created
- Create a new branch for this commit and start a pull request.
  - Branch-name: branch-patch-batman
- Click: Propose new file


Then we go to this window:
- Click: Create pull request

![pull-request-1](images/pull-request-1.png)

After that, we have this:  
Clicking in 'Merge pull request' will accept the proposed changes and commit.  

![pull-request-2](images/pull-request-2.png)

But, in the lower part, by clicking in 'Close with comment' we can discard that pull request.  
Also, we can start a debate about if the commit is convenient or not, it's possible to mention other people to include them in the debate.  

![pull-request-3](images/pull-request-3.png)

The repo will continue the same, unless the pull-request is finally accepted.

There are two possibilities in 'Merge pull request':
- Create a merge commit: This creates a commit. Default option.
- Squash and merge: Joins this commit with the previous one, so there won't be an extra commit.

So:
- Merge pull request -> Create a merge commit -> Confirm merge
- We can delete the branch.

![pull-request-4](images/pull-request-4.png)

Finally, we can check the changes in the repo.

In the end, to have this changes in the local-repo:  
`git remote update`  
`git status -uno`  
or  
`git fetch`  
then  
`git pull`  
`git lg`  

![pull-request-5](images/pull-request-5.png)

---

***f) Git Fetch***

--> Adding a file

In GitHub -> master-branch -> Location: git-course/historia/
- New File -> Name: historia.flash.md
- Text: 
~~~
## Historia de Flash

Flash (conocido tambi??n como The Flash y traducido en espa??ol: Destello) es el nombre de varios superh??roes ficticios que aparecen en los c??mics estadounidenses publicados por DC Comics. Creado por el escritor Gardner Fox y el artista Harry Lampert, el "Flash" original apareci?? por primera vez en Flash Comics #1 (fecha de portada de enero de 1940 / mes de noviembre de 1939). Apodado el "Corredor Escarlata", todas las encarnaciones del Flash poseen "s??per velocidad", que incluye la capacidad de correr, moverse y pensar extremadamente r??pido, tambi??n puede atravesar la materia s??lida, usar reflejos sobrehumanos y aparentemente violar ciertas leyes de la f??sica, como superar la velocidad de la luz.
~~~
- Commit message: Create historia.flash.md (default)
- Commit new file

Now, inside 'historia' folder there are three files:
- batman.md
- historia.flash.md
- superman.md

The name is not like the other, it can be changed:
- Click in the file -> click in the pencil -> Change name: historia.md
- Commit message: Rename historia.flash.md to flash.md (default)
- Commit changes
  - I created another commit by mistake, so at the end there'll be four commits.
  
Then, for some reason we have to delete 'flash.md'.
- Click in the file -> Click in the garbage-icon
- Commit message: Delete flash.md
- Commit changes

--> Checking the commits

- In the repo -> click in the commits -> there we can see all the commits run in the remote-repo.
  - But, it's like if nothing would've happened because we created a file and then delete it.

![fetch-1](images/fetch-1.png)

However, if we go to our local-repo, we cannot see those commits.
- Using 'git lg' will tell us that both repos are side by side. 
- But, for real, the remote-repo is 4 commits ahead the local-repo.
- The last commit they had in common was *897326d*.

![fetch-2](images/fetch-2.png)

If we don't want to do a 'pull, merge or anything' we just want to update the repos.  
`git fetch`  
`git lg`  

![fetch-3](images/fetch-3.png)

After, to sync the repos:  
`git pull`  
`git lg`

It's recommendable always doing a 'fetch' before run any other command.

---

***g) Comments in the commits***

In GitHub it's possible to add comments to any line by clicking in a blue-button +.  
- Some options for comments are: edit, hide, delete.

---

***h) GitHub Flow***

Related links:
- [GitHub flow](https://docs.github.com/es/get-started/quickstart/github-flow)
- [Repo relacionado](https://github.com/SvanBoxel/release-based-workflow/issues/1)

![github-flow-1](images/github-flow-1.png)

---
---

## 9 GITHUB - ADVANCED
[Index](#index)

### 9.1 Fork - Clone - Collaborations

Case 1: Added as a collaborator 
- If we have our project in a remote-repo (i.e. GitHub), it's possible to 'clone' it to any computer as a local-repo. Eventually we'll 'push' our changes to the remote-repo.  
  - If we are added as a 'collaborator' in a remote-repo that's not ours, we'll be able to do the same as if the remote-repo was ours.

Case 2: Non-collaborator
- If there is somebody else's remote repo, and we're not collaborators.
  - We'll be able to clone it, make local commits, create branches, but we won't be able to do 'pushes' to GitHub.
  
Case 3: Forking the repo
- In case we want to be collaborators in a remote-repo, maybe we have good ideas, or we found some errors that we know how to solve.  
- Considering this remote-repo as public in GitHub, we can do a 'fork':
  - google/maps -> fork -> mi_usuario/maps (here we'll have total access)

In the third case, whenever we have done some changes in our forked-repo that we want to show to the original owners, we have to do a 'pull request'.
- Consider that the forked-repo is like a branch. So, the original-repo can merge the changes we send in a 'pull request'.

![fork-1](images/fork-1.png)

---

### 9.2 Forking - Cloning 
[Index](#index)

***Forking another repo***

In this part we'll work with another repo.  
[Use this repo](https://github.com/Klerith/legion-del-mal)

![fork-2](images/fork-2.png)

Note that the 'Add file' option is enabled.  
- Creating or uploading a file will create a 'fork'.

Click in 'Fork'.

![fork-3](images/fork-3.png)

Click in 'Create fork'.  
This repo is completely ours, we can do anything with it.

![fork-4](images/fork-4.png)

***Cloning our repo (forked)***

Copy the URL -> Open GitBash (choose the location) -> Command:  
`git clone [URL]`  

We'll have a folder 'legion-del-mal', we can change the name to '10-legion-del-mal'. There's no problem because the repo is inside the folder.  
Open the folder with IntelliJ to see its content.  

From GitBash:  
`cd [project-location]`  

It's possible to execute commands like:  
`git lg`  
`git remote -v`  
~~~
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (fetch)
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (push)
~~~

We can delete something in a file:  
`git commit -am "README updated"`  
`git push`  

---

### 9.3 Pull Request 
[Index](#index)

To Do: Cloned-repo -> push -> Forked-repo -> PR -> original-repo  

![pr-1](images/pr-1.png)

**In the cloned-repo (local)**  

Change 'miembros.md'.  
`git commit -am "miembros.md changed"`  

Create a file in 'aspirantes' folder, name: 'freddy.md', and add some text.  
`git add .`  
`git commit -m "freddy.md added"`

`git push`  (send 2 commits)  

**In our forked-repo (remote)**  

In the interface there'll be an option 'Fetch upstream'. This is to update our forked-repo from the original-repo.  
What we care about is the option 'Contribute'.
- By clicking it, it'll tell us if our forked-repo is a number of commits ahead/behind the original-repo.  
- Open Pull request.
- We can see the changes before creating the pull request.
  - If in this point we notice that we forgot some changes.
  - We can go to the cloned repo, do the changes, push them.
  - And then we can refresh the webpage and now there'll be an extra commit.
- Create Pull Request.
  - Add a message.
  - Check in 'Allow edits by maintainers'.
  - Create pull request.

At this point the owners and contributors of the original-repo will receive an email because of our PR.  
Also, now the control passes to them, because only those with 'write access' to the original-repo can 'merge pull requests'.  

It's possible to cancel the PR by clicking 'Close pull request'.  

**In the original-repo (remote)**  

The admin has to accept or decline our PR.  
Every PR has an icon: green: open / purple: closed (merged) / rojo: declined  

Revision: The admin checks the PR.  
There are 4 tabs: Conversation / Commits / Checks / Files changed

'Conversation' is to interact with the PR-requester
- Check the changes, make a reaction.
- For example, in a file changed the admin can write a comment: "Why you did this?" -> Click: Add single comment  
  - We receive the message, and we can reply.

'Commits' is to check the commits one by one.

'Files changed' -> Button: Review changes:  
- Here the admin can do one of three things:
  - Comment: Submit general feedback without explicit approval.
  - Approve: Submit feedback and approve merging these changes.
  - Request changes: Submit feedback that must be addressed before merging. (like a checklist)

Maybe the admin doesn't want that 'miembros.md' change.
- Write a comment
- Select: Request changes
- Submit review
  - We receive that message.

**In the cloned-repo (local)**  

`git lg` to see where we did the action the admin requests us to change.  
In the previous commit, copy the hash.  

`git checkout [hash] miembros.md` .. to undo the changes in that file.  
`git add .`   
`git commit -m "miembros.md changes reverted"`   
`git push`  

**In our forked-repo (remote)**  

What was requested is done.  
Send a confirmation message.  

**In the original-repo (remote)**  

'Files changed' to review everything.  
- Click in 'Review changes', write a message
- Check 'Approve'
- Submit review

To finish: there are three options:
- Create a merge commit
  - All commits from this branch will be added to the base branch via a merge commit.
- Squash and merge
  - The # commits from this branch will be combined into one commit in the base branch.
- Rebase and merge
  - The # commits from this branch will be rebased and added to the base branch.

Click in 'Squash and merge' 
- Write a message-commit, it's a good idea appending the contributor name with @.
- Click in 'Confirm'.

The 'PR icon' will change to purple color.  
We will receive a message, and also the contributors.  

---

### 9.4 Updating our forked-repo
[Index](#index)

***Theory*** 

`git pull`  
It is used to sync our local-repo to the remote-repo.  
This concept is valid in both cases: when we have cloned a repo, and when we have forked a repo.  

In the image, what I have called before as 'original-repo' it's usually called 'upstream'. And, what I have called as 'remote-repo', it's called 'origin'.  
So, we'll have two remote-repos: origin and upstream.

`git remote add upstream <original-repo>` .. to add the original repo.  
`git fetch upstream` .. to sync the upstream and the local.  
`git pull` .. and then again the cyle: git push -> pull request

![upstream-1](images/upstream-1.png)

***Practice: upstream -> origin -> local*** 

Being in the forked-repo, there is an option 'Fetch upstream'.
- There we can see the status, maybe it can be:
  - The original-repo is 1 upstream commit from the forked-repo.
- We have two options: Compare / Fetch and merge
  - Fetch and merge: now both remote-repos are in sync.

Being in the local-repo, to sync the local with the forked-repo (origin):
`git pull`  

***Practice: upstream -> local*** 

Copy the original-repo URL: https://github.com/Klerith/legion-del-mal.git  
Being in the local-repo.  

`git remote -v`
~~~
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (fetch)
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (push)
~~~

- This means that we read (fetch) from the 'origin', and we write (push) also to the 'origin'.  
- But, our project can have many remote-repos.  
- Usually if there is a remote-repo which will be only to fetch info, it's called as 'upstream'.  

To add another remote-repo:  
`git remote add upstream https://github.com/Klerith/legion-del-mal.git`  

To check the remote-repos:  
`git remote -v`
~~~
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (fetch)
origin  https://github.com/freddy-alexis-ht/legion-del-mal.git (push)
upstream  https://github.com/Klerith/legion-del-mal.git (fetch)
upstream  https://github.com/Klerith/legion-del-mal.git (push)
~~~

- Even when it shows the 'push' in the 'upstream' we know we can't push to it.  

If we have used 'git pull -u origin master', then the next time we can use just 'git pull'.  
The same goes for the 'git fetch'.  
So if we want to fetch from the upstream the command has to be:  
`git fetch upstream`  
`git pull upstream master`  

Depending on the situation, the pull can turn into a: fast-forward or rebase  
Then, considering a rebase:  
`git commit -am "local updated from upstream"`  (to merge the changes in our local)  
`git rebase --continue`  (mark the conflict as solved)  
`git lg`  
`git commit -am "README updated from Fork"`  
`git push`  

---

### 9.5 Workflow introduction (master-feature)
[Index](#index)

Considering a scenario like this:

![workflow-1](images/workflow-1.png)

When working on groups, usually every developer creates a feature-branch, in this case from the master.  

Considering we have all branches in local, we can check other people's progress:  
`git fetch`  .. to sync our branch  
`git branch -a`  .. to list all branches  
`git checkout rama-x`  .. to go to rama-x

To merge changes to master and push them to the remote-repo:  
`git checkout master`  
`git merge rama-x`  
`git push`  

A better approach would be to push our local changes to our remote-branch.  
`git push origin rama-x`  
And then: pull request  

---

### 9.6 Task: Create a new repo and a Tag
[Index](#index)

***Task 1: Create a repo***

In this task we'll work with [this repo.](https://github.com/klerith/avengers)

![task-1](images/task-1.png)

GitHub interface -> Code -> Download zip (this doesn't download the commits-history)  
Unzip and rename to '11-avengers' -> Open with IntelliJ.

In GitHub: Create a repo: 'avengers' -> Public -> Create  
When creating a repo with nothing inside, it shows this:  

![task-2](images/task-2.png)

Open GitBash, we can follow this commands:  
~~~
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/freddy-alexis-ht/avengers-test.git
git push -u origin master
~~~

***Task 2: Create a Tag***

Working with tags:  
`git tag my-release` .. tag with random name.  
`git tag` .. to see all tags.  
`git tag -d my-release` .. to delete a tag.  

`git tag -a v0.1.0 2cbcce8 -m "Version: alpha"` .. tag in a commit.
`git show v0.1.0` .. tag description.  
 
So, if we want to create a tag, the command could be:  
`git tag -a v0.0.1 cc1f326 -m "Version: Alpha"`  
`git push --tags`  

In the remote repo..  
Releases -> Create a new release -> Choose the tag -> v0.0.1
- Release title: Versi??n Alpha del producto.  
- Description: Add some text
- Check: This is a pre-release
  - To indicate that this isn't ready for Production. This is like a release candidate.
- Publish release

![task-3](images/task-3.png)

---

### 9.7 Feature branch - Workflow via Pull Request
[Index](#index)

It's possible to invite other people to participate in our GitHub-repo.  
Settings -> Access: Collaborators  

We're not supposed to work in branch-master, it's better feature-branch.  

Local-repo, we can see the current branch with:  
`git status`  
`git branch`  

***Creating another branch in Local***

In Local, master branch.  
Create 'villanos.md', add some text. Don't track it in master.  
By creating files and the branch in this way, those files won't be considered in master, they won't even appear as untracked, they will be part of the just created branch.  

Create the new branch and be in it:  
`git checkout -b br-villanos`  
`git add .`  
`git commit -m "villanos.md added"`  

At this point, the recently created branch is local. If we go to GitHub, only 'master' will be there.  
The command to push our branch is a bit complex, so we can do this:  
`git push`  

And we'll have the correct command:  
~~~
fatal: The current branch br-villanos has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin br-villanos
~~~

Run the command:  
`git push --set-upstream origin br-villanos`

![feature-1](images/feature-1.png)

And, in our GitHub-repo, it will ask if we want to 'Compare & pull request'.  

![feature-2](images/feature-2.png)

Click in 'Compare and pull request'.  
- base: master <- compare: br-villanos   (able to merge)
- PR Title: vilanos.md added
- Comment: add some text.  
- Create pull request

GitHub checks if there's conflict or not.  
In this case it says:
- This branch has no conflics with the base branch
  - Merging can be performed automatically.
- If the PR haven't been merged, it's still possible to add some local changes, commit and push (git push) them to the remote-repo.
  - In villanos.md add an extra line: Evil Domingo
  - Commit: `git commit -am "Evil Domingo added to villanos.md"`
  - Push: `git push`  (it's not necessary to add the destination)
- That last commit will be part of the PR.

![feature-3](images/feature-3.png)

- After it has been checked by the admin and other contributors
- Merge pull request -> Create a merge commit -> Confirm  
- Don't delete br-villanos branch yet.

![feature-4](images/feature-4.png)

Now it's done, we can check the commits:  

![feature-5](images/feature-5.png)

Go to 'Branches', it's possible deleting it from GitHub.  
Delete 'br-villanos' branch.  
But, in Local the branch is still there, so we should:  
`git checkout master`  
`git fetch`  
`git pull`  
`git branch -d br-villanos`  

---

### 9.8 Feature branch - Reviewing partners' job
[Index](#index)

***Worker A: Changes GitHub-repo***

GitHub-repo: avengers-test -> branch: master  
It's possible to create a branch in the interface.  
br-misiones .. it'll be used by my team to create 'missions'.  
If the branch doesn't exist, GitHub creates it, and take us to it.  
- New File -> misiones.md -> Add some text.
- Commit message: Create misiones.md   (default)
- Click: Commit new file

Obviously, in GitHub, branch 'master', there is no 'misiones.md'.  

***Worker B: In Local***

Maybe at this point, Worker-A tell us to check the changes he uploaded to br-misiones.  
So, in our Local we can get those changes with this commands:  
`git branch` .. only 'master'  
`git pull`  
`git lg`  
`git branch` .. still only 'master'  
`git pull -all`  
`git branch` .. only 'master', 'br-misiones' should be also here  

![feature-6](images/feature-6.png)

But, the other branches are there, we just don't see them. Run:  
`git branch --all`  
~~~
* master
  remotes/origin/br-misiones
  remotes/origin/br-villanos
  remotes/origin/master
~~~

To change to worker-A's branch:  
`git checkout br-misiones`  
~~~
Switched to a new branch 'br-misiones'
branch 'br-misiones' set up to track 'origin/br-misiones'.
~~~

***Working on worker-A's branch, but in Local***  

Now, that branch is visible:  
`git branch`
~~~
* br-misiones
  master
~~~

Because of this change, in IntelliJ we have that branch set: worker-A's branch  
Let's say that, for some reason (i.e. vacation) worker-A is not present, so we add a line to 'misiones.md', because it was necessary:  
~~~
### Missions

* Investigate Dr. Doom plans
* Capture Red Skull
~~~

`git commit -am "misiones.md updated"`  
`git push`  

Now that change is in the GitHub-repo, br-misiones branch.

***GitHub repo - Pull request***  

Click in 'Compare and pull request' -> Check
- Create pull request
- Add a title
- Add some descriptions
- Create pull request.
- We'll see:
  - This branch has no conflicts with the base branch  
    Merging can be performed automatically.
- Merge pull request
- Confirm

Go to 'master' branch and now we'll have there 'misiones.md'.  
Delete 'br-misiones' from GitHub.  

***Branches in Local***  

Unused branches should be deleted, see how many we have:  
`git branch --all`  
- 'br-misiones' (green) current local branch
- 'master' (white) another local branch
- The rest (red) remote branches

![feature-7](images/feature-7.png)

---

### 9.9 Delete unused branches
[Index](#index)

While we work we'll have many branches we won't use anymore.  
In this case, 'br-misiones' wasn't even ours, it's a partner's branch.  

`git checkout master`  
Here I don't have the last changes, i.e. misiones.md. But, there's no problem, because I know all that is in the GitHub-repo master branch.  

`git fetch`  
`git pull`  

`git branch -all`
~~~
* master
  br-misiones
  remotes/origin/master
  remotes/origin/br-misiones
  remotes/origin/br-villanos
~~~

So, we don't need 'br-misiones', and remember that in remote only 'master' exists.  

To delete a local branch:  
`git branch -d br-misiones`

Trying to delete the ref to a remote branch:  
`git push origin :br-misiones`

It can't delete those branches because they don't exist in remote.
- If we had run this command when the branch existed in local and remote, it'd have been ok. But, we first delete the branch in remote, that's why it's not working.  

In cases like this we have to run this command:  
`git remote prune origin`

![feature-8](images/feature-8.png)

---

### 9.10 Production branch
[Index](#index)

Together with 'master' branch, usually some other branches are kept.  
Maybe they're considered historical, stable, or similar. They are still used, and still receiving maintenance.  
In these cases, branches are tagged, so they have a version in particular.  
These other branches can also be called 'production-branches'.  

***Local***

`git checkout -b br-kitkat`  

In Local: villanos.md: add villain: Unfriendly Lucas, and delete a villain.  

`git commit -am "Lucas added to villanos.md"`  
`git push`  
`git push --set-upstream origin br-kitkat`  

So, 'br-kitkat' will be kept, won't be deleted.  
It's recommendable to tag the branch.  

`git tag -a v1.0.0 -m "KitKat v1.0.0 - stable"`

![production-1](images/production-1.png)

***GitHub***  

Create release from tag
- Release title: Versi??n KitKat v1.0.0
- Description
- Publish release

It's important to tag it.   
If someone deletes br-kitkat in remote, we still can use the tag.

As we still have br-kitkat in Local, we can push it and Remote will have that branch again.  
But, what about if I had deleted that branch in Local and the reference to the remote too?  

`git checkout master`  
`git branch -d br-kitkat`  
`git remote prune origin`  

---

### 9.11 Recovering the production branch: br-kitkat
[Index](#index)

***Recovering via Local***

`git tag`  
`git checkout v.1.0.0`  

Notice that at this point we're not precisely in a branch, it's the tag.  

![production-2](images/production-2.png)

To create a branch in that point:
`git checkout -b br-kitkat`  
`git push`  
`git push --set-upstream origin br-kitkat`  

![production-3](images/production-3.png)

Now, the branch 'br-kitkat' is in remote.  
Lastly, in local we can 'checkout' to master to continue our work.  

***Recovering via GitHub***

In Local:  
`git checkout master`  
`git branch -d br-kitkat`  

To delete the branch in GitHub-repo from our local:  
`git push origin :br-kitkat`

But, now I want br-kitkat branch in the remote.  
Interface: branch (combo-box) -> tags -> v1.0.0  
Tags (combo-box) -> Find or create a branch: Write: br-kitkat  

![production-4](images/production-4.png)

-> In case branches and tags are deleted in local and remote, we would have to use 'git reflog'.  
-> Tags shouldn't be deleted.

---
---

## 10 GITHUB ISSUES - MILESTONES - CONTRIBUTORS
[Index](#index)

Milestone .. something important we need to happen (hito), some features should be implemented, some bugs should be fixed
It's a part of a project, helps us not to forget we're supposed to finish something.

issue .. is like a question (don't know what to do), are very versatile they can even be used to send messages.

### 10.1 Issues

[Ver GitHub Issues](https://docs.github.com/en/issues)

If it's not enabled: Settings -> Options -> Issues  

***a) Crete an issue*** 
Issue: 
- To make questions. 
- To tell the repo's admin I have an error.  
- To collect all bugs and problems that should be solved before our work goes to Production env.  

By default, the filter is set to: 'is:issue is:open'

![issue-1](images/issue-1.png)

If filters are deleted, it will display the actions we did that have a '#': 

![issue-2](images/issue-2.png)

New issue:
- Title: Some Avengers are missing.
- Description (to create two tasks)
~~~
# Request
Please add these Avengers to thelist.
- [ ] Nick Fury
- [ ] Spiderman
~~~
- Click: Submit new issue

---

***b) Close an issue***

It's possible to create an issue from a part of another issue.

![issue-3](images/issue-3.png)

Note that we already had #1 and #2, the issue is #3.  
These are references, the numbers are tracked by GitHub.  
An issue can be deleted, but it shouldn't be because of 'integrity'. It's better not to lose track of ##.  

An issue created by mistake should have a comment like in the image.  

![issue-4](images/issue-4.png)

It also can be locked:  
The admin will continue being able to comment, but others won't.

![issue-5](images/issue-5.png)

*-> A real issue will be closed like this:*  
It says we should add 'Nick Fury' and 'Spiderman' in miembros.md.

Go to the Local -> miembros.md -> Do the addition
>This was done in the br-kitkat branch, maybe it should've been done in another feature-branch:  

`git commit -am "Nick Fury and Spiderman added to miembros.md"`  
`git push`  

Go to GitHub and do the pull-request.  
- Title: Merge: members added in misiones.md
- Click: Create pull request
- Check 
  - In the line where the Avengers were added a comment can be added
  - I.e. #3 This resolves the issue             
    - The #3 added is a link to the issue
- Click: Merge pull request
- Confirm merge

![issue-6](images/issue-6.png)

*-> Another way to close an issue*  

Another way to link the issue and the solution is:  
Add a comment to the issue saying:
- This was solved with this: [commit-hash] -> Close issue

---

***c) Deleting an issue***

When trying to delete an issue, this will be displayed:
- This cannot be undone
- Only administrators can delete issues
- Deletion will remove the issue from search and previous references will point to a placeholder

---

***d) Close an issue with a commit***

Remote: New issue
- Title: Delete Spiderman
- Create issue (let's say the ref is: #5)

Local:
- miembros.md: delete Spiderman
- `git commit -am "Fixes #5: Spiderman deleted in miembros.md"`
- `git push`

Remote:  
It uses the ref to fix the issue and close it.

---

***e) Issue Templates***

Settings -> Set up templates  
- Add template
  - Bug report: Standard bug report template
  - Feature request: Standard feature request template
  - Custom template: Blank template for other issue types
- Select one
- Edit / Preview
- Click: Propose changes
- Commit changes (everything is tracked by GitHub)

New Issue
- It suggests if it's a bug report or other.

![issue-7](images/issue-7.png)

This is useful when the project has a lot of interaction.
- Many people report bugs, or demand new features, or similar. In this way everything can be tracked.  

---

***f) Labels (in Issues)***

These are issue organizers. There are some default: 

![labels-1](images/labels-1.png)

While interacting with the issue, labels can be selected.  
Labels can be used to filer issues.  

Labels can be added to the Issue Templates too.

---

### 10.2 Milestone (hito)
[Index](#index)

[Ver GitHub Milestone](https://docs.github.com/en/issues)

You can use milestones to track progress on groups of issues or pull requests in a repository.  

When you create a milestone, you can associate it with issues and pull requests.  

- To better manage your project, you can view details about your milestone. From the milestone page, you can see:
  - A user-provided description of the milestone, which can include information like a project overview, relevant teams, and projected due dates
  - The milestone's due date
  - The milestone's completion percentage
  - The number of open and closed issues and pull requests associated with the milestone
  - A list of the open and closed issues and pull requests associated with the milestone

For example, we can group issues in a milestone for these:
- **Beta launch:** File bugs you need to fix before you can launch the beta of your project. It's a great way to make sure you aren't missing anything.
- **October Sprint:** File issues you'd like to work on in October. A great to focus your efforts when there's a lot to do.
- **Redesign:** File issues related to redesigning your project. A great way to collect ideas on what you work on.  

GitHub -> New Issue  
Milestone -> Name: Beta launch -> Create and assign to new milestone  
Submit new issue

It's possible to add another issue, a due date and a description.

![milestone-1](images/milestone-1.png)

There are two issues in this milestone.

![milestone-2](images/milestone-2.png)

![milestone-3](images/milestone-3.png)

![milestone-3](images/milestone-4.png)

---

### 10.3 Adding Contributors
[Index](#index)

Settings -> Collaboratos -> Confirm password  

![contributors-1](images/contributors-1.png)

Add people -> an email will be send  
The other person will have to Accept the invitation.  

- The contributor cannot access to the repo-settings.
- This person can clone, can even destroy the repo, so be carefull who you invite.  
- Clicking in the trash-icon we can delete the collaborator.

It's possible to transfer the ownership of the repo to a contributor:
- Settings -> General -> Danger zone
- Transfer ownership ...

![transfer-1](images/transfer-1.png)

---
---

## 11 WIKIS - PROJECTS - GITHUB PAGES - INSIGHTS
[Index](#index)

### 11.1 Wikis

GitHub: repo: avengers-test  

Wikis are like the Wikipedia or our project.  
- User documentation/manual.
- The way the repo works: installation, requirements to initiate the project.
- It can be edited by contributors.
- It creates unique URLs to share.

Settings:

![wikis-1](images/wikis-1.png)

***Create the first/home page***

![wikis-2](images/wikis-2.png)

When the headers are used, GitHub creates anchor-tags.
- Click there -> copy the unique URL -> when the URL is used it'll take us exactly to that place.

![wikis-3](images/wikis-3.png)

***Create new page***

New page: Name: Instalaciones

![wikis-4](images/wikis-4.png)

***Linking pages***

Let's say: Clicking in 'Write here' should take us to 'Contact' webpage.

![wikis-5](images/wikis-5.png)

Edit 'Home' -> Click in the 'link' menu option
- Write the text.
- Write the URL or the name fo the page.
- Save page.

![wikis-6](images/wikis-6.png)

Test it by clicking in the link (in Home), it will go to the Contact page.

***Ordering pages***

As we can see here, Home is first, and the rest is in alphabetical order.  

![wikis-5](images/wikis-5.png)

To re-order the pages: click in 'Add a custom sidebar'.  

![wikis-7](images/wikis-7.png)

![wikis-8](images/wikis-8.png)

---

### 11.2 Projects
[Index](#index)

Projects is like a whiteboard where we can classify items.
- Tasks to do.
- Urgent tasks to do.
- Tasks that someone has to do.

Some teams create a new repo to use the Projects feature.  
In this case we'll use it inside this repo.

Click in 'Projects'
- This takes us to the main page (out of the repo).
- After creating the Project (without any template)
  - Name: Avengers
- Go to the repo (avengers-test)
  - Projects -> Add project -> select 'Avengers' -> Click in it
  - View -> Boards (there are three columns by default).

![projects-1](images/projects-1.png)

![projects-2](images/projects-2.png)

To edit the view:  
Settings -> Status

![projects-3](images/projects-3.png)

The interface is not like in the video, it has changed.  
For example, in the video it's possible to select specific options for each column.  

***Working in Todo column***

- It's possible to add:
  - Draft: It's like a note.
  - Issues: The issues created can be in here

For example:  
Create an issue: Name: Team tasks  
Description:  
~~~
### TODO:
- [ ] Tarea 1
- [ ] Tarea 2
- [ ] Tarea 3
- [ ] Tarea 4
~~~
Submit new issue  

![projects-4](images/projects-4.png)

Add the issue to the board:

![projects-5](images/projects-5.png)

When we finish the 4 tasks we can close the issue. Automatically, the card will move from 'In Progress' to 'Done'.  

![projects-6](images/projects-6.png)

---

### 11.3 GitHub Pages - User and Repo
[Index](#index)

Free Hosting: GitHub Pages is useful to deploy a website in GitHub.  
- It serves files: .html, .css, .js, .md. 
- Side server programming languages are discarded: .php, .java, ... But if our code make HTTP-requests to a backend, it works fine. 
- It is used to create a portfolio.

It can be used to create a webpage for a specific repo, or a webpage for the user.  

***a) Creating a webpage for the User/Organization***

Our URL will be: freddy-alexis-ht.github.io  
By the end of this, it should take me to my webpage (doesn't exist yet).

New repo
- Name: freddy-alexis-ht.github.io
- Public
- Create repository
- Settings
- Pages
  - Source/Branch: Here a branch or a folder can be selected, I don't have any now, so leave it.


To add a theme, 'master' should exist (in the video, themes are there to be selected, not in my case)  
However, [here are the themes](https://pages.github.com/themes/)

For example, choose 'Architect'. It'll take us to its repo -> copy the content of 'index.md'.  
Create a file in our repo: name: index.md -> paste the text.  
Now, if we go to: <freddy-alexis-ht.github.io> we'll see our webpage.

![page-1](images/page-1.png)

Commit changes in 'index.md' are not immediate, they might take a few minutes to be visible in our webpage.

Some links:
- [Add a theme](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
- [GitHub Blog](https://github.blog/)

---

***b) Creating a webpage for a specific repo/project***

The repo or branch used to deploy a website ends up being Public, so be careful.  
The master branch or any other can be used to deploy the website, but usually it's better to have a folder for that purpose.  

In Local: 11-avengers' repo:  
- `git checkout -b br-web`  
- Create directory: docs  
- Create static content: index.html  

index.html  
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Freddy's Page</title>
</head>
<body>
    <h2>Mi t??tulo</h2>
    <hr>
    <p>Hola Mundo</p>
    <script src="./js/app.js"></script>
</body>
</html>
~~~

Inside 'docs' create the directory 'js', and in it this file:  
app.js  
~~~
console.log("Hola mundo desde JavaScript");
~~~

![page-2](images/page-2.png)

`git add .`  
`git commit -m "Website added"`  
`git push`  
`git checkout master`  
`git merge br-web`  
`git push`  

In GitHub:  

![page-3](images/page-3.png)

Settings -> Pages -> Source: main -> Select folder: /docs -> Save  

After a few seconds, we'll see the image. The webpage is: https://freddy-alexis-ht.github.io/avengers-test/  
Notice that the webpage uses HTTPS, it has its own Certificate.

![page-4](images/page-4.png)

---

### 11.4 Insights
[Index](#index)

Statistical information about the activity in the repo 'avengers-test': 

![insight_1](images/insight_1.png)

All the options shown are good. A useful one is 'Network':

![insight_2](images/insight_2.png)

There is not much info in the previous repo because it's new. But, if we go to repo like 'facebook-react':  

![insight_3](images/insight_3.png)
![insight_4](images/insight_4.png)
![insight_5](images/insight_5.png)
![insight_6](images/insight_6.png)

---
---

## 12 ORGANIZATIONS - TEAMS
[Index](#index)

### 12.1 Organizations

An Organization can be considered as an IT Department.  
Every organization have Teams: Infrastructure, Development, DB, Support  
In every team there can be more teams:
- Development Team, can have a team for App-A, another for App-B.
- Also, a Dev Team for Juniors, this team would have some access limitation due to their seniority.

The idea is to classify people, tasks, projects, in general: resources.  

***a) Creating an Organization***

New -> Organization  

- [Organization Plans](https://github.com/organizations/plan)

Something great is that even in the Free-tier we have 'Unlimited public/private repositories'.  

![org-1](images/org-1.png)

- Organization account name: Domingo's Life
  - It's important to set a name we won't change, because a URL will be created with it.
  - There it says: "Your URL will be: https://github.com/Domingo-s-Life"
- Contact email
- Personal account

![org-2](images/org-2.png)

In this view, we have to give some info -> Submit

![org-3](images/org-3.png)

In my account I can have private and public repos, and also in my organization I can have private and public repos.  

---

***b) Transfer a repo to an organization***

To transfer the domain of our repo to an Organization, we need the name of the latter.  

Being in the main-user -> repo: avengers-test -> Settings -> Transfer ownership
- Write the organization's name.

![org-4](images/org-4.png)

![org-5](images/org-5.png)

---

### 12.2 Teams
[Index](#index)

***a) Teams and repos***

With the Organization's user
- Teams, it's like a little organization

![teams-1](images/teams-1.png)

- New team
- Team name: Developers
- Description
- Team visibility
  - Visible: To every organization member
  - Secret: Only visible to team members

![teams-2](images/teams-2.png)

Click in Developers-Senior -> Repositories -> Add: avengers-test

![teams-3](images/teams-3.png)

---

***b) Privileges***

At this point our organizations has 3 teams and 1 repository.  

All team-members in 'Developers-Senior/avenger-test' by default have 'Read' privileges.  
- Read: fork, pull-request, clone, read.
- Admin: Issues, manage PR, merge, include collaborators.

![teams-4](images/teams-4.png)

Changing permissions applies to all team-members.

---

***c) About the members***

Tab: People  
- 2FA: Two-Factor Authentication.  
- Private: Your membership is only visible to other members of this organization.
- Public: Your membership is visible to everyone and is displayed on your public profile.
- Role: Owner/Member

![teams-5](images/teams-5.png)

---
---

## 13 GIST
[Index](#index)

***a) About Gist***

It's public or secret, but can't be private. Everyone will see it.  
- Secret: It won't be found by the GitHub search-engine, but anyone with the URL can access to it.

It can be considered as a public mini-repo (follow changes, who did what, ...).  

It's useful in situations like:
- Share info with the community.
  - Publish code/text to students/friends that we don't want them to write again, or search.
  - Share code, binaries (pdf, images, zip).
- Create repo of very useful code: 
  - How to obtain a random number between two limits.
  - How to use a specific class or interface.
  - Email validation.
  - Recommended steps installation.

***b) Create a Gist***

New gist
- Gist description: Java: method for random
- File name: RandomNumber.java
- Write code
- Create secret gist
- Copy the URL
  - In an Incognito window: paste the URL -> accessible

![gist-1](images/gist-1.png)

- Changes are also tracked.
- The same gist can have many files.

---

### 13.1 Gist plugins - Personal tokens
[Index](#index)

![gist-2](images/gist-2.png)

***Link my GitHub Gist with my IntelliJ***

- Create token access
  - In GitHub -> main view -> Settings (account)
  - Developer settings -> Personal access tokens
  - Name: Gist-Intellij
  - No expiration
  - Check: Gist
  - Generate token -> copy and save it

- GitHub Gist plugin in IntelliJ  
  - IntelliJ -> Plugin -> Gist -> Install
  - Settings: Check the way gist works in the IDE
  - Alt + I to insert gists
    - Add GitHub account
    - Enter token

![gist-3](images/gist-3.png)
![gist-4](images/gist-4.png)

Changing the token, now it works. Gists can be inserted easily in the IDE.  

![gist-5](images/gist-5.png)

It's possible to create Gists from IntelliJ.
- Git tab -> GitHub -> Create Gist..
- Immediatelly it'll be visible in GitHub Gist

---

### 13.2 All Gists
[Index](#index)

GitHub Gist -> All Gists -> This is the worldwide repo for gists.  

![gist-6](images/gist-6.png)

---
---

## 14 SSH
[Index](#index)

Local
~~~
mkdir .ssh  
cd .ssh  
ssh-keygen -t rsa -C "freddy.alexis.ht@gmail.com"  
~~~

It generates two files in 'C:\Users\Usuario\.ssh'. Use the id_rsa.pub  

GitHub -> Settings -> SSH -> New SSH Key  
- Title
- Key: id_rsa.pub copy and paste -> Add SSH key

`ssh -T git@github.com`  
Message: Permanently added 'github.com,[IPv4]' (RSA) to the list of known hosts.  

Clone a repo using SSH:  
`git clone [repo-URL] demo-name`  
Go inside 'demo-name' folder and work as if 'HTTPS' would have been used.  
