
# QCM

### git init

What is **true** about the `git init` command?  
  
_Multiple correct answers expected._

- It is a one-time command to initialize a Git repository
- It creates a new **.init** subdirectory in your current working directory
- Doing the first `git commit` after `git init` will create a new `master` branch
- It has to be run every time you switch branches

### Amending a commit (simple)
Language knowledge (60 pts)

What is **true** regarding the `--amend` flag of a `git commit` command?  
  
_Multiple correct answers expected._

- It can modify only the last commit
- It can modify multiple previous commits
- It can modify only the commit message
- It can modify the commit message as well as add new files to the same commit

### git blame
Language knowledge (60 pts)

Which command would display which revision and author last modified each line of a `index.html` file?

- git show -b index.html
- git show --blame index.html
- git blame index.html
- git show -blame index.html

### [Github] Fork
Language knowledge (60 pts)

If you want to freely make changes to a project without affecting the original, which feature of Github can you use?

- Pull request
- Fork
- Branch
- Clone

### git clone files
Language knowledge (40 pts)

We assume that the default branch is the master branch.

When `git clone <remote repository>` is executed, which files will be added to the local working directory?

- The files of the first commit made to the remote repository on the master branch
- No files will be fetched, only an empty repository will be created
- The latest version of the remote repository files on the master branch
- The latest version of the remote repository files on the most recently created branch

### HEAD and tilde
Language knowledge (40 pts)

Refer to the image below which shows the commit history.  
![](https://static.codingame.com/work/servlet/fileservlet?id=15822086073993)  
The `HEAD` is at commit **F**. You realize that the last few commits you made were incorrect and you want to change your current branch to point to C and make all your local files to be the same as the ones in commit **C**.  
  
Which of the following commands will you execute?

- git reset --hard HEAD~2
- git reset --hard HEAD~3
- git reset --hard HEAD~4
- git reset --hard HEAD~~

### git commit
Language knowledge (40 pts)

What does the  `git commit` command do?

- Commits the staged snapshot to the remote repository
- Commits the staged snapshot to the local repository
- Commits all changes to the staging area
- Commits all changes to the remote repository skipping the staging area

### .gitconfig
Language knowledge (40 pts)

Which file lets you specify Git’s global configuration settings?

- .git
- .gitconf
- .settings
- .gitconfig

### -m flag
Language knowledge (20 pts)

Which flag lets the user type the commit message inline with the `git commit` command?

- -m
- -i
- -l
- -a

### [Github] README.md
Language knowledge (20 pts)

Which file is used to show the project summary/documentation at the root of your repository in Github?

- README.md
- README.doc
- document.md
- introduction.doc

# Text

### Reset hard

Refer to the image below regarding `git status` output:  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=15874295958102)  
  
Which command should be executed to remove all files from the staging area and also modify the working directory to match the most recent commit?

### git merge

You have been assigned bug #33 . You create a new branch `bugfix33` and commit the needed changes on that branch.  
  
Refer to the image below:  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=15822281606349)  
  
Read through all the git commands that are executed. Write the next command to merge those changes into the `master` branch (assuming `master` branch is up-to-date).

### git clone

A remote repository is present at ** https://github.com/hellogit/hello.git**.  
  
Write the command to create a copy locally in your current directory.

### git push

Which Git command will you use to send changes committed in your local repository to a remote repository?  
Your answer should have the format `git xxxxx`.

### git status #1

Which command would you execute to get the list of locally modified files before committing anything to the repository?





# Code
