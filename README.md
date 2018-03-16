# GIT - Version Control System
Developed in 2005 by Linus Torvalds to make a core of Linux OS. Its on GNU GPL licence.
Better then SCM tools like Subversion or CVS.

> UDEMY Bootcamp by Colt Steele

## REPO - repository
folder with application/project witch is tracked by GIT

GIT REPO is only a folder with backup files on your computer.
BUT You can synchronize this files with GITHUB or Atlassian BITBUCKET (competitor of git), web apps to cooperate and share projects.

# GIT Commands in terminal:

## GIT init
*Just type `git init` when you are on a directory to follow*
Initializing GIT to follow some folder and control versions of files/folders in it.
So its good to keep all versions of a Project/App in one directory and make a REPO for this directory.

It makes hidden folder ".git" inside this directory (.dot usualy mean that this is hidden)
*In command line type: `ls -a` to see hidden content ("a" for "all")*

### STOP Tracking
just remove ".git" directory


## GIT status
Ask GIT for a status of a working tree of a project.
Tell us if there are some new files or changes (modifications) to add and to commit
If you changed a name GIT will se a file as deleted and You have to add new file

## GIT add
Tell GIT to track a fille from tracked folder.
But it still don't add it to a REPO untill we will commit it.
GIT don't track all files in a folder automaticaly after INIT, we have to add them.

> IMPORTANT: we can add all changes / files at once ussing dot ".":
> `git add .`

## GIT commit -m "messege / description"
SAVED POINT IN TIME (we can go back to this point)
We can add many new filles and change them, but they wont be in a REPO untill we will COMMIT them.
While commiting we can add description of changes, what we are commiting.

> IMPORTANT: there is convention to use present tense, like:
> `git commit -m "add app.js file"` (NOT "added")

## GIT rm - REMOVE file

## GIT mv - Change a name or move a file to other directory


## GIT log
history of commits with date, author, description and unical ID like hashline


### HEAD - is a pointer in time.
HEAD show us a place in time (commit) on wich we are working now.
Usualy it show us "master" becouse we work on main branch (the newest version)
But when we use "git checkout ID" it will show us HEAD detached at 7ac6b76 (a begining of ID we are working)
> *detached = oderwany, oddzielny*


## GIT checkout
to chack out previous code (usualy without changing enythig, just look)
Get back to some saved (commited) point in a past. We check commit ID by "git log" and type:
`git checkout 7ac6b76cbac6b7ca7bac879acb (ID)`

it wont work (abort) if we have some changes/filles wich haven't been commited

If we want to go back to MASTER (newest version) we don't need it's ID, just type:
`git checkout master`

to DISCARD changes (e.g. take back deleted file) use command:
`git checkout -- <file-name like: app.js>`

## GIT BRANCH <branch-name>
If we want to have 2 diferent versions of an aplication (we dont know witch way we wont to go, want make some changes in old commit we are checking out) we can make a new branch (it have its own commits history and we can develope 2 branches independently)
To make a new branch we could type:
`git branch <branch-name> <commit id>`
`<commit id>` is optional, but it will make branch from this commit (not from a HEAD commit)

To create new branch and switch to it immediately type:
`git checkout -b <new-branch-name>`
(so "-b" tels us to make a new branch when we are checking out)

we can also create a new branch from previous commit and go to it:
`git checkout -b <new-branch-name> <commit-id>`


GIT tutorial from Ian:
https://www.youtube.com/watch?v=_4d1gpmcke4&list=PL86ehqHzxhy4XX_qZZE_5mrp38WGZRzTO&index=11

### GIT branch
(without a <branch-name>) it will show a list of branches

### GIT show-branch
To see all branches AND they commits history

### Removing a branch
`git branch -d <branch-name>`

### GIT checkout <branch-name>
Take HEAD to this branch, we can work on it. Make some changes.


## GIT MERGE <branch-name>
it merge 2 branches to one, merging also files.
If we want to marge some branch to master, the HEAD should be on Master
IT WILL AUTOMATICALY MERGE FILES WITH CODE AND SHOW DIFERENCES IN A FILLE.
USUALY WE HAVE TO CHECK / FIX MANUALY EFECTS OF MERGING, add it and commit it.


### REVERT GIT REPO
https://stackoverflow.com/questions/4114095/how-to-revert-git-repository-to-a-previous-commit

> NOTE:
> Most of developers use and remember only about 7 GIT commands,
> and have to check on internet how to do something rare, like REVERTING GIT REPO.

If You want to go back to some point and continue development from this point (canceling some part of writen code, e.g. if it havent work) we can REVERT to some old commit ID and commit it again to start working with this old version:

```
git revert --no-commit 0766c053..HEAD
git commit -m "comment: REVERT BACK to <ID>"
```
This will revert everything from the HEAD back to the commit hash, meaning it will recreate that commit state in the working tree as if every commit since had been walked back. You can then commit the current tree, and it will create a brand new commit essentially equivalent to the commit you "reverted" to.

(The `--no-commit` flag lets git revert all the commits at once- otherwise you'll be prompted for a message for each commit in the range, littering your history with unnecessary new commits.)

This is a safe and easy way to rollback to a previous state. No history is destroyed, so it can be used for commits that have already been made public.


# GIThub.com

1. Create new repository on Github ("+" on the top-right of a page)

2. use a command from github to add github to local GIT reporistory:
`git remote add origin https://github.com/LucasMatuszewski/udemy-intro-to-git.git`

3. push the local repository to github:
`git push -u origin master`

Sometimes you have to update your version of git or git for windows.
Usualy you have to login or set user.email and name:
```
git config --global user.email "you@example.com"
git config --global user.name "LucasMatuszewski"
```

## GIT remote
`git remote add <shortcut-name> <remote-url>`
To add new remote repository, e.g. from github.com 

`git remote -v`
Show all added remote repositories with URL

## GIT clone
`git clone <remote-repository-url>`
To clone remote repository on our disc, e.g. from Github.com

## GIT fetch
`git fetch <remote-repository-name>`
When we have cloned repository, we can download remote changes to local disc usigng "fetch"


## GIT push
To send local commit to remote repository
`git push -u <remote-repository-name> <branch>`

`git push -u origin master`
Is the same as:
```
git push origin master
git branch --set-upstream master origin/master
```

If we use `-u` we tell git to track remote branch "master"
Without `-u` we have to tell GIT wich branch to track with `--set-upstream`


# GIT-Flow vs GitHub Flow
http://scottchacon.com/2011/08/31/github-flow.html

## GitHub Flow:
Deploy all changes fast without "releases"

1. Anything in the master branch is deployable (**hard rule**)
2. To work on something new, create a descriptively named branch off of master (ie: new-oauth2-scopes)
3. Commit to that branch locally and regularly push your work to the same named branch on the server
4. When you need feedback or help, or you think the branch is ready for merging, open a pull request
5. After someone else has reviewed and signed off on the feature, you can merge it into master
6. Once it is merged and pushed to ‘master’, you can and should deploy immediately

That is the entire flow. It is very simple, very effective and works for fairly large teams - GitHub is 35 employees now, maybe 15-20 of whom work on the same project (github.com) at the same time. I think that most development teams - groups that work on the same logical code at the same time which could produce conflicts - are around this size or smaller. Especially those that are progressive enough to be doing rapid and consistent deployments.

## GIT-Flow:
Deploy releases (like v1.0, v1.2, v2.0) containing many changes, after tests and bug-fixes.

https://jeffkreeftmeijer.com/git-flow/

https://github.com/nvie/gitflow