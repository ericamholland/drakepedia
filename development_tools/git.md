# Git
## Overview
Git is a *version control system*, allowing you to keep track of multiple versions of a piece of software and coordinate changes with other developers. While manually making backup copies and emailing them around is fine for small programs, a tool like git becomes essential for larger projects.
## Setup
### Installation
You can check if git is installed on your system with this command:
```
git --version
```
If it isn't, you can download it from the [git website](https://git-scm.com/).
### Configuration
It's a good idea to run the commands below (with "your name" replaced appropriately) before using git for the first time:
```
git config --global user.name "Your Name"
git config --global user.email yourname@yourdomain.edu
git config --global core.editor emacs
git config --global color.ui true
```
### Creating a Repository
A *repository* is a set of snapshots of your files. (Git is actually clever enough to save space by only storing the *differences* between these snapshots, but you don't have to think about that.)

First create a directory and put a simple file in it -- say, `file.txt`.

Now, within that directory, initialize the repository with this command:
```
git init
```
To see the status of the repository, use this command:
```
git status
```
The output tells you that you are on the master branch (more about branches later), you haven't made any *commits* (snapshots), and your file is still untracked. You have to explicitly tell git which files to keep track of. There are often files you *don't* want to put under version control, such as compiled programs and huge data files.

To add a file to version control:
```
git add file.txt
```
To make your first commit:
```
git commit -am 'Initial project version'
```
The part at the end is the commit message, explaining what you changed.

If you check the status again, you will see that there is now "nothing to commit" -- your current workspace of files matches the most recent commit. In general, working with git is a cycle of making changes to your files and then committing them.
### Committing
Edit a file. Alternately, create a new file and add it to version control.

Before committing, it's a good habit to always run `git status` to make sure things are in the state you think they're in.

Now commit:
```
git commit -am 'My poem is now twice as long'
```
Check the status again to make sure it worked.

You should *always* be in a clean state before trying to do anything else with git. Usually this means committing. Occasionally you will decide that you instead want to throw away all of your work since the last commit. If you are *absolutely sure* that you want to do this, here is the command:
```
git reset --hard HEAD
```
### Working With Past Commits
You can view the history of your repository with this command:
```
git log --pretty=oneline --graph --all
```
Each line represents one commit. It shows the hash (a number that identifies the state of the files) and the commit message. Some additional information like `HEAD -> master` tells you which one is the current commit.

For a example to work with, suppose the output of the log command looks like this:
```
* b3615564012377ecab73e0b693aa7542f84e39df (HEAD -> master) My poem is now twice as long
* 456b316a09a835b22b8822c0f1fd0906c12ae2a5 Initial project version
```
If you want to go back to the previous version, do something like this:
```
git checkout 456b31
```
The hexadecimal number at the end is a prefix of the hash, enough to uniquely identify it. If you now examine your files, you'll see that they're back to the way they were after the first commit!

The newer commit (b36155...) is still in the repository. Once something is in the repository, it's fairly difficult to destroy it. There are git commands that allow you to modify the past, but it's a Bad Idea; you're likely to end up becoming your own grandparent or tearing a hole in the spacetime continuum.

To go back to the newer commit, you could use a similar `checkout` command. A much better idea is to use
```
git checkout master
```
to reattach `HEAD` to the front of the `master` branch. Never make commits in a detached HEAD state; it could cause you to lose work.
### Branches
### Remote Repositories
## Additional Resources
### Online
### Print
## Questions
1. :star::star: How often should you commit?
## Answers
1. Often -- several times an hour. Part of the point of git is to allow you to go back to a previous commit if you make a mistake, so you want to have many options of how far to go back.