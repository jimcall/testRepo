================================================================================
Git - Version Control System
================================================================================
http://git-scm.com/download/win

--------------------------------------------------------------------------------
Installation
--------------------------------------------------------------------------------
 . comes with 'Git Bash' - Unix command-line interface (easier to use)
 . Git commands still work from Windows command-line interface
 . can use a Git client, such as TortiseGit, but then you don't learn as much

--------------------------------------------------------------------------------
Commands
--------------------------------------------------------------------------------
Source: https://www.youtube.com/watch?v=SWYqp7iY_Tc

 a) Create empty repository in cwd (or re-initialise it)
    git init

 b) Register user name and email
    git config --global user.name  'Jim Callaghan'
    git config --global user.email 'james.andrew.callaghan@gmail.com'

 c) Add a file to staging area (what will be committed to repository)
    git add <file>

 d) Show what files are staged, untracked (not added), modified, etc.
    git status

 e) Remove file from staging area
    git rm --cached <file>

 f) Add ALL files to staging area
    git add .

 g) Discard changes to files
    git checkout -- <file>

 h) Commit changes
    git commit (-> opens default editor for you to add a comment)
    git commit -m '<comment>'

 i) Ignore file - files or directories to ignore when committing
    .gitignore
      changes.log
      /bogusDir

 h) Create a new branch
    git branch <branch name>

 i) Change to a branch
    git checkout <branch name>

 j) List branches
    git branch

 k) Display file history
    git log <file>

--------------------------------------------------------------------------------
GitHub - Remote Git Repository
--------------------------------------------------------------------------------
 a) Create an account

 b) Create repository (top right-hand corner - plus sign)
    e.g. testRepo

 c) List remote repositories (none)
    git remote

 d) Add the local repository as a remote repository
    git remote add origin https://github.com/jimcall/testRepo.git

 e) List remote repositories (origin)
    git remote

 f) Add branch (master) to remote repository (pop-up login)
    git push -u origin master
    
    NB. Refresh the GitHub URL and you'll see the files

 g) Push local file to remote repository (committed file locally)
    git push
 
 h) Pull remote file from remote repository (added file from browser)
    git pull

================================================================================
