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

 k) Display history of a file
    git log <file>
      commit 3e4c524f84c23af2242f5aee082e84c94cc28205 (HEAD -> master, tag: 1.0.0, origin/master)
      Author: Jim Callaghan <james.andrew.callaghan@gmail.com>
      Date:   Fri Mar 9 12:05:04 2018 +1100
      
          Added comments re merging branches and viewing config values
      
      commit a65d4f6c01b63605efd21795a9eeecf0650db614 (project1)
      Author: Jim Callaghan <james.andrew.callaghan@gmail.com>
      Date:   Fri Mar 9 10:49:46 2018 +1100
      
          minor changes
      ...

    git log --pretty=oneline <file>
      3e4c524f84c23af2242f5aee082e84c94cc28205 (HEAD -> master, tag: 1.0.0, origin/master) Added comments re merging branches and viewing config values
      a65d4f6c01b63605efd21795a9eeecf0650db614 (project1) minor changes
      c630db0b14734ec9ec47481e07b4e502dc129a3b Added readme.txt and changed 'ignore file' contents


 l) Display history of all files (output displayed in less by default)
    git log

 m) Merge a branch back to the trunk
    git checkout master     (change to the trunk branch)
    git merge project1      (pull changes from other branch)
      -> Automatic merge failed; fix conflicts and then commit the result
         git status         (confirm what's required)
         Edit file; search for <<<<<<<, >>>>>>>; select what to keep; save file
         git add .          (accept new version of file/s)

 n) Tags
    list all tags
      git tag
      
    Add a tag
      git tag -a 1.0.0 -m 'master version 1.0.0'
      
    List specific tags
      git tag -l 1*

--------------------------------------------------------------------------------
GitHub - Remote Git Repository
--------------------------------------------------------------------------------
 a) Create an account (jimcall/gmail)
    https://github.com/jimcall

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

 g) Push commits made locally to remote repository
    git push [<remotename>] [<branchname>]
    git push  origin         master
    git push
    
 h) Push a single tag (same command as pushd commits)
    git push  <remotename> <tagname>
    git push   origin       1.0.0

 i) Pull remote file from remote repository (added file from browser)
    git pull
    
 j) Display config values
    git config -l                                  (list all)
      core.editor='C:\Program Files (x86)\Notepad++\notepad++.exe' -multiInst -notabbar -nosession -noPlugin
      user.name=Jim Callaghan
      user.email=james.andrew.callaghan@gmail.com
      remote.origin.url=https://github.com/jimcall/testRepo.git
      branch.master.remote=origin
      branch.master.merge=refs/heads/master
      ...

    git config --get remote.origin.url             (specific value)
      https://github.com/jimcall/testRepo.git

    git config --get-regexp remote*                (regexp values)
      remote.origin.url https://github.com/jimcall/testRepo.git
      remote.origin.fetch +refs/heads/*:refs/remotes/origin/*
      branch.master.remote origin

================================================================================
