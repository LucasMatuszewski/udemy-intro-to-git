>UDEMY Bootcamp by Colt Steele

#GIT - Version Control System
Developed in 2005 by Linus Torvalds to make a core of Linux OS. Its on GNU GPL licence.
Better then SCM tools like Subversion or CVS.

##REPO - repository, folder with application/project witch is tracked by GIT

GIT REPO is only a folder with backup files on your computer.
BUT You can synchronize this files with GITHUB or Atlassian BITBUCKET (competitor of git), web apps to cooperate and share projects.

#GIT Commands in terminal:

##GIT init
*Just type "git init" when you are on a directory to follow*
Initializing GIT to follow some folder and control versions of files/folders in it.
So its good to keep all versions of a Project/App in one directory and make a REPO for this directory.

It makes hidden folder ".git" inside this directory (.dot usualy mean that this is hidden)
*In command line type: "ls -a" to see hidden content ("a" for "all")*

###STOP Tracking - just remove ".git" directory


##GIT status
Ask GIT for a status of a working tree of a project.
Tell us if there are some new files or changes (modifications) to add and to commit
If you changed a name GIT will se a file as deleted and You have to add new file

##GIT add
Tell GIT to track a fille from tracked folder.
But it still don't add it to a REPO untill we will commit it.
GIT don't track all files in a folder automaticaly after INIT, we have to add them.

> IMPORTANT: we can add all changes / files at once ussing dot ".":
> git add .

##GIT commit -m "messege / description"
SAVED POINT IN TIME (we can go back to this point)
We can add many new filles and change them, but they wont be in a REPO untill we will COMMIT them.
While commiting we can add description of changes, what we are commiting.

> IMPORTANT: there is convention to use present tense, like:
> git commit -m "add app.js file" (NOT "added")

##GIT rm - REMOVE file

##GIT mv - Change a name or move a file to other directory


##GIT log
history of commits with date, author, description and unical ID like hashline


###HEAD - is a pointer in time.
HEAD show us a place in time (commit) on wich we are working now.
Usualy it show us "master" becouse we work on main branch (the newest version)
But when we use "git checkout ID" it will show us HEAD detached at 7ac6b76 (a begining of ID we are working)
*detached = oderwany, oddzielny*


##GIT checkout
to chackout previous code (usualy without changing old version)
Get back to some saved (commited) point in a past. We check commit ID by "git log" and type:
> git checkout 7ac6b76cbac6b7ca7bac879acb (ID)

it wont work (abort) if we have some changes/filles wich haven't been commited

If we want to go back to MASTER (neewest version) we don't need ID, just type:
> git checkout master

###BRANCH
If we want to have 2 diferent versions of an aplication (we dont know witch way we wont to go, want make some changes in old commit we are checking out) we can make a new branch (it have its own commits history and we can develope 2 branches independently)
To make a new branch we could type:
> git branch <branch name> <commit id>
> <commit id> is optional, but it will make branch from this commit (not from a HEAD commit)

###GIT show-branch
To see all branches and they commits history

###GIT checkout <branch-name>
	Take HEAD to this branch, we can work on it.

##GIT MERGE <branch-name>
it merge 2 branches to one, merging also files.
If we want to marge some branch to master, the HEAD should be on Master
IT WILL AUTOMATICALY MERGE FILES WITH CODE AND SHOW DIFERENCES IN A FILLE.
USUALY WE HAVE TO CHECK MANUALY EFECTS OF MERGING


###REVERT GIT REPO
https://stackoverflow.com/questions/4114095/how-to-revert-git-repository-to-a-previous-commit

> NOTE:
> Most of developers use and remember only about 7 GIT commands,
> and have to check on internet how to do something rare, like REVERTING GIT REPO.



