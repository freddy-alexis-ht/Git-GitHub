## 1. PROJECT CONFIGURATION AND BASIC COMMANDS

For this course it's necessary to have git version 2.10+

---

### 1.1 Local-repo and Remote-repo

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

---

### 1.2 Project creation

- Open IntelliJ -> New project -> Java: 1.8
  - Project name: pry-git
  - Project location: ..../pry-git

---

### 1.3 Initial Commands

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

---

### 1.4 Course project

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

`git checkout -- .` .. reconstruct the project as it is in the last commit.  
Remember that it only cares about the tracked files.  
If a file was created, this command wouldn't erase it, because it would be in 'untracked' state.

---

***c) Change branch name: main -> master***

`git branch` .. display the branches.
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
HEAD -> main .. the last commit was made in branch 'main'.  
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

***b) Update commit messages***

Commit with a mistaken message:  
`git commit -m "incorrect message`

Rewriting the commit message:  
`git commit --amend -m "correct message`

It can be checked with:
`git log`

---

***c) Revert commit***

If after commit we feel we'd want to add some other changes to that previous commit:  
`git reset --soft HEAD^` .. 'HEAD^' is equivalent to 'HEAD^1', es un commit antes del HEAD (last one).  
If it's need to go to other previous commits: HEAD^2, HEAD^3, but it's not recommendable to go to far.

Check the logs wit 'git log'.

Then add the changes with 'git add .' and write the correct commit.  
`git commit -m "another correct message`

---
### 2.2 Module '03-heroes' - Time travel, reset and reflog

***a) Working with the project***

![module-03-heroes](images/module-03-heroes.png)

Consider these commits were made in different times.  
Take into consideration the folders hierarchy in the git commands.  
`git add 03-heroes/src/README.md`  
`git commit -m "README added"`

- The files will be added and committed one by one.
  - Add the README.md: message: README added
  - Add the README.md: message: misiones added
  - Add the README.md: message: heroes added
  - Add the README.md: message: ciudades added
  - Add the README.md: message: historia folder added

At this point, we notice that 'historia' folder has two files in it.  
`git commit --amend` .. displays info about the last commit.
- For example, in 'Changes to be commited' we can see that there are two files in the folder 'history'.
- So, it would be better to change the commit-message.

![amend](images/amend.png)

- To change the *commit-message*:
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
.. there'll be two M's (modified)
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

- For some reason it's necessary to go back to the commit 'ciudades added' (hash: bacc4ca)  
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

We realized that the commits were ok, and we want to undo all the resets (soft, mixed, hard), we want to go back to were 'Linterna verde' and 'Robin' were added (hash: ea4bf49).    
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

`git status`

![rename](images/rename.png)

We have what we wanted, everything in the logs.

![rename-2](images/rename-2.png)

---

***b) Deleting***

`git rm 03-heroes/src/save.md`  
When the file is deleted, it's still in the stage (to be committed).
- It can be brought back with:  
  `git reset --hard` .. but it's better to use:  
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

***a) Merge types***

- Fast-forward: There are no changes in the master-branch, so the changes in the other-branch can be merged easily. Each commit will be part of the master-branch, just like if the other-branch wouldn't have been created.  
- Automatic merge: There were changes in the master-branch, but there are no conflicts with what's been changed in the other-branch.
- Manual merge: In both branches the same code was modified, git will ask us to solve it manually. After the problem is solved, git creates the 'merge-commit' and we can continue.

![fast-forward-merge](images/fast-forward-merge.png)
![merge-conflict](images/merge-conflict.png)

---

### 3.1 Project '04-merge' - Fast-forward merge

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
    · 6f850f5 - (4 minutes ago) Merge 'master with branch 'br-villanos' - Freddy2 (HEAD -> master)  
    |\  
    | · 6ed8522 - (18 minutes ago) Notes added - Freddy2 (br-villanos)  
    | · e0e9975 - (22 minutes ago) Doomsday added - Freddy2  
    · | 238ae61 - (14 minutes ago) Daredevil deleted - Freddy2  
    |/  
    · 2cbcce8 - (74 minutes ago) Flash reverso added - Freddy2  
~~~

---

### 3.3 Project '04-merge' - Manual merge (conflicts)  

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

To create a tag in any commit .. copy the hash:  

`git tag -a v0.1.0 2cbcce8 -m "Version: alpha"`  

![tag-4](images/tag-4.png)

Tag description:

`git show v0.1.0`  

![tag-5](images/tag-5.png)

---
---

## 5. GIT STASH - TEMPORAL STORAGE

***Stash***  
It's like a vault where we can put files, even those untracked by git.  

Scenario:
- We're working on a branch, it can be 'master' or other branch.  
- We're asked to go to the last commit, but we don't want to commit the changes we have so far.
- We save those un-committed changes with Stash.
- We go to the last commit and do what we have to, then we can recovery our progress.  

This action can cause scenarios just like the ones we saw with 'merge'.  
**Tip:** It's better to save only one stash and attend to it as soon as possible. Having many stashes can be confusing.  

***Rebase***  
It allows to join/split commits, to rename commits, ...  
**Tip:** Use it only if we haven't merged our changes to other repo. Also, don't change the History, because maybe they were already merged to a main repo.  

---

### 5.1 Stash   

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
4. Necesitamos más comida
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

Este es un repositorio de los héroes.
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

In the image, we can see that 'git stash' displays a similar message as with 'git status'.  
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

Este es un repositorio de los héroes.
~~~

After:  
~~~
# Notas

Este es un repositorio de los héroes.
Texto agregado.
~~~

`git stash`  
Now we're in the last commit, and make changes over the same file we have an stash.  

~~~
# Objetivos

Este es un repositorio de los héroes.
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

Este es un repositorio de los héroes.
Texto agregado.
~~~

---

***c) Stash with conflicts: Auto-merging***

**Working in the same file, and in the same line**  

Before (master-branch):  
~~~
# Objetivos

Este es un repositorio de los héroes.
Texto agregado.
~~~

After (master-branch):
~~~
# Objetivos del repositorio

Este es un repositorio de los héroes.
Texto agregado.
~~~

`git stash`  
The code goes back to this:  
~~~
# Objetivos

Este es un repositorio de los héroes.
Texto agregado.
~~~

Then (master-branch), a change and a commit:  
~~~
# Objetivos del repositorio principal

Este es un repositorio de los héroes.
~~~

`git commit -am "README updated first line"`  
`git stash pop`  

There is conflict, the stash is not dropped.  

![stash-5](images/stash-5.png)  
![stash-6](images/stash-6.png)  

We have to solve the conflict. In the end, we'll keep the file like this.  

~~~
# Objetivos y Notas

Este es un repositorio de los héroes.
Texto agregado.
~~~

`git commit -am "stash conflict solved"`  

Remember the stash wasn't dropped.  
`git stash list`  

---

### 5.2 Stash Avanzado  

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

In this part this project will be used:  

![rebase-2](images/rebase-2.png)

In the image, the last commit in common is 'acea380: Actualización de las misiones'.  
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
pick 158ba9e Se agrego a la liga: Volcán Negro
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
pick 158ba9e Se agrego a la liga: Volcán Negro
p 141071a Agregamos el archivo de las misiones completadas
s 9ecb331 Actualizamos dos misiones completadas al momento
s c731cc5 Actualizamos misiones completadas
~~~

---

### 6.3 Rebase Reword

`git rebase -i HEAD~4`  

Interactive window:
~~~
pick 300c014 Misiones nuevas agregadas
pick 158ba9e Se agrego a la liga: Volcán Negro
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
pick 158ba9e Se agrego a la liga: Volcán Negro
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

### 6.3 Rebase Edit

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

Have in mind that Git doesn't manage access control to the repo.  
- For this task we have some 'hosted services' like: GitHub, Bitbucket, ...
- And, managed by ourselves like: Gitosis.  
  - Gitosis is a tool which provides access control and remote management for hosted Git repositories. It allows for fine-grained management of read and write access over SSH, without requiring that the users have local system accounts on the server.  

Gitosis oficial links:
- [What is Gitosis?](https://wiki.archlinux.org/title/gitosis#:~:text=Gitosis%20is%20a%20tool%20which,system%20accounts%20on%20the%20server.)
- [Instal and configure](https://github.com/res0nat0r/gitosis)

Useful link:
- [Save user and pass of GitHub](https://docs.github.com/es/get-started/getting-started-with-git/caching-your-github-credentials-in-git#platform-windows)

---

### 7.1 GitHub - Push

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
'origin' is the name of te remote repo.  
'master' is the local branch we want to push.  
'-u' sets 'master' by default, so in the next time it will be enough 'git push'.  

---

### 7.2 New remote repo

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

Delete the project '09-heroes' .. this is to simulate that we lose our work.  
There's no problem, because it's in GitHub.  

GitHub -> Code (Clone) -> HTTPS -> Copy the URL.  
`git clone [URL]`  

Note the repo is cloned with the name as it's in the remote: git-course.  

![clone-1](images/clone-1.png)

---

### 7.6 Pushing changes to remote-repo

`git status`  
`git add .`  
`git commit -m "README.md updated again"`  

With 'git lg' we can see that the local-repo is 1 commit ahead the origin (remote-repo).  

`git push`

***Conflict***

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

