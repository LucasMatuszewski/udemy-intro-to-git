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

##GIT checkout
get back to some saved (commited) point in a past. We check commit ID by "git log" and type:
> git checkout 7ac6b76cbac6b7ca7bac879acb (ID)

it wont work (abort) if we have some changes/filles wich haven't been added

