

#----------------------4. Git Config------------------------#
# User Name:- 
-> Your name will be attached to your commits. Set it with:
# Ex:- 
git config --global user.name "kschandan113"

# Email Address
-> Your email is also attached to your commits. Set it with:
# Ex:- 
git config --global user.email "kschandan113@gmail.com"

# Use --global to set the value for every repository on your computer.
# Use --local (the default) to set it only for the current repository.

# Why Configure Git?
    -> Git uses your name and email to label your commits.
    -> If you do not set these, Git will prompt you the first time you try to commit.
    -> Now you have added the minimum of configuration needed to start using Git.

# Viewing Your Configuration
# EX:- List All Setting
git config --list
op:- 
user.name=kschandan113
user.email=kschandan113@gmail.com

# Example: View a Specific Setting
git config user.name
op:-
kschandan113

# Changing or Unsetting Config Values:-
    -> To change a value, just run the git config command again with the new value.
    -> To remove a setting, use --unset:
# EX:-
git config --global --unset code.editor

# Default Branch Name:-
    -> Set the default branch name for new repositories (for example, main instead of master):
# EX:- Set Default Branch Name
git config --global init.defaultBranch main

# Configuration Levels
There are three levels of configuration:
    -> System (all users): git config --system
    -> Global (current user): git config --global
    -> Local (current repo): git config --local

The order of precedence is:
    -> Local (current repo)
    -> Global (current user)
    -> System (all users)

The reason to use the different levels is that you can set different values for different users or repositories.
This can be used for example to set different default branches for different repositories and users.

# Example: Set a Local Config:- 
    -> Local settings only apply to the current repository.
# EX:-
git config user.name "Project Name"

# EX:- Set a Global Config
    -> Global settings apply to all repositories for the current user.
git config --global user.name "Global Name"

# Example: Set a System Config
    -> System settings apply to all repositories for all users.
git config --system user.name "System Name"

#---------------------------5. Get Started with Git-----------------------------#
# Key Steps to Get Started
    -> Create a project folder
    -> Navigate to the folder
    -> Initialize a Git repository

# Creating Git Folder:-
    -> Start by creating a new folder for our project.
# EX:-
mkdir Git_Repo
cd Git_Repo

    -> mkdir creates a new directory.
    -> cd changes our working directory.
    -> Now we are in the correct directory and can initialize Git!

Note: Open Git Bash Here (Windows)
If you're using Windows, you can open Git Bash directly in your project folder:
    -> Right-click the folder in File Explorer
    -> Select Git Bash Here
This opens a terminal window in the correct location.

# Initialize Git:-
    -> Now that we are in the correct folder, we can initialize Git on that folder:
# EX:-
git init   # Initialized empty Git repository in /Users/user/myproject/.git/

# What is a Repository?
    -> A Git repository is a folder that Git tracks for changes.
    -> The repository stores all your project's history and versions.

# What Happens When You Run git init?
    -> Git creates a hidden folder called .git inside your project.
    -> This is where Git stores all the information it needs to track your files and history.

# Example: Show Hidden .git Folder (Linux/macOS):-
    ls -a

# Troubleshooting
    -> git: command not found
        Solution: Make sure Git is installed and added to your PATH. Restart your terminal if needed.
    -> Permission denied
        Solution: Try running your terminal as administrator (Windows) or use sudo (macOS/Linux) if needed.

#---------------------------------Git New Files------------------------------------#
# What is a New File?
    -> A new file is a file that you have created or copied into your project folder, but haven't told Git to watch.
    
-> Here are the key things to know:
    * Create a new file (with a text editor)
    * ls - List files in the folder
    * git status - Check which files are tracked
    * Understand untracked and tracked files

# Create a New File:-
* Your new Git repository is empty.
* Let's add a file using your favorite text editor, and save it in your project folder.
* If you need help creating a file, see our HTML Editors page.
* For this example, we'll use a simple HTML file:

# List Files in the Directory:-
    -> To see which files are in your project folder, use the ls command:
# EX:-
ls 

* ls lists all files in the current folder.
* You should see index.html in the output.

# Check File Status with git status:-
# EX:-
  git status

Git sees index.html, but it is untracked (not yet added to the repository).

# What is an Untracked File?
    -> An untracked file is any file in your project folder that Git is not yet tracking.
    -> These are files you've created or copied into the folder, but haven't told Git to watch.

# What is a Tracked File?
    -> A tracked file is a file that Git is watching for changes.
    -> To make a file tracked, you need to add it to the staging area (covered in the next chapter).

# Troubleshooting
    * File not showing up with ls: Make sure you saved it in the correct folder.
      Use pwd to check your current directory.
    * File not listed in git status: Make sure you are in the correct folder and that you saved the file.

# Git Staging Environment:-
# What is the Staging Environment?
    -> The staging environment (or staging area) is like a waiting room for your changes.
    -> You use it to tell Git exactly which files you want to include in your next commit.
    -> This gives you control over what goes into your project history.

Here are some key commands for staging:
    * git add <file> - Stage a file
    * git add --all or git add -A - Stage all changes
    * git status - See what is staged
    * git restore --staged <file> - Unstage a file

# Stage a File with git add
    -> To add a file to the staging area, use git add <file>:
# EX:-
    git add index.html
-> Now index.html is staged. You can check what is staged with git status:

# Stage Multiple Files (git add --all, git add -A)
    -> You can stage all changes (new, modified, and deleted files) at once:
# EX:-
    git add --all
git add -A does the same thing as git add --all

# Check Staged Files with git status

# How to Unstage a File:-
    -> If you staged a file by mistake, you can remove it from the staging area (unstage it) with:
# EX:-
git restore --staged simple.html

* Now index.html is no longer staged. You can also use git reset HEAD index.html for the same effect.

# Troubleshooting:-
* Staged the wrong file? Use git restore --staged <file> to unstage it.
* Forgot to stage a file? Just run git add <file> again before you commit.
* Not sure what's staged? Run git status to see what will be committed.


#-----------------------------------Git Commit----------------------------------------------------#
## What is a Commit?
* A commit is like a save point in your project.
* It records a snapshot of your files at a certain time, with a message describing what changed.
* You can always go back to a previous commit if you need to.

Here are some key commands for commits:
    -> git commit -m "message" - Commit staged changes with a message
    -> git commit -a -m "message" - Commit all tracked changes (skip staging)
    -> git log - See commit history

## How to Commit with a Message (-m)
    -> To save your staged chnages use (git commit -m "your message")
# EX:-
git commit -m "First release of Hello World!"

## Commit All Changes Without Staging (-a):-
* You can skip the staging step for already tracked files with git commit -a -m "message".
* This commits all modified and deleted files, but not new/untracked files.
# EX:- 
git commit -a -m "quick update"

* Warning: Skipping the staging step can make you include unwanted changes. Use with care.
* Note: git commit -a does not work for new/untracked files. You must use git add <file>   
  first for new files.

# What happens if you try to commit a new file with -a?
git commit -a -m "Try to commit new"

# Write Multi-line Commit Messages:-
* If you just type git commit (no -m), your default editor will open so you can write a detailed, multi-line message:
# EX:- 
git commit
Write a short summery on the first line, leave a blank line, then add more detail below.

# Commit Message Best Practices:
* Keep the first line short (50 characters or less).
* Use the imperative mood (e.g., "Add feature" not "Added feature").
* Leave a blank line after the summary, then add more details if needed.
* Describe why the change was made, not just what changed.

# Other Useful Commit Options:-
* Create an empty commit:
    git commit --allow-empty -m "Start project"
* Use previous commit message (no editor):
    git commit --no-edit
* Quickly add staged changes to last commit, keep message:
    git commit --amend --no-edit

# Troubleshooting Common Commit Mistakes:-
* Forgot to stage a file?
    If you run "git commit -m "message"" but forgot to "git add" a file, just add it and commit again. Or use "git commit --amend" to add it to your last commit.
* Typo in your commit message?
    Use "git commit --amend -m "Corrected message"" to fix the last commit message.
* Accidentally committed the wrong files?
    You can use "git reset --soft HEAD~1" to undo the last commit and keep your changes staged.

# View Commit History (git log):-
* To view the history of commits for a repository, you can use the "git log" command:
EX:- git log
* for a shorter view, use "git log --online"
Ex:- git log --online

* To see which files changed in each commit, use "git log --stat:"
EX:- git log --stat


#----------------------------------Git Tagging----------------------------------------#
# Key Commands for Tagging:-
* git tag <tagname> - Create a lightweight tag
* git tag -a <tagname> -m "message" - Create an annotated tag
* git tag <tagname> <commit-hash> - Tag a specific commit
* git tag - List tags
* git show <tagname> - Show tag details

# What is a Tag?
    -> A tag in Git is like a label or bookmark for a specific commit.
    -> Tags are most often used to mark important points in your project history, like releases (v1.0 or v2.0).

* Tags are a simple and reliable way to keep track of versions and share them with your team or users.

# Some common tag types include:
    * Releases: Tags let you mark when your project is ready for release, so you (and others)  
      can always find that exact version later.
    * Milestones: Use tags to highlight major milestones, like when a big feature is finished  
      or a bug is fixed.
    * Deployment: Many deployment tools use tags to know which version of your code to deploy.
    * Hotfixes: If you need to fix an old version, tags make it easy to check out and patch  
      the right code.

## Create a Lightweight Tag
    -> A lightweight tag is just a name for a commit.
    -> It's quick and simple, but does not store extra information.

* Annotated vs Lightweight Tags
    -> Annotated Tag: Stores author, date, and message.
       Recommended for releases and sharing with others.
    -> Lightweight Tag: Just a simple name for a commit (no extra info, like a bookmark).
* EX:- 
git tag v1.0

# Create an Annotated Tag (-a -m):-
    -> An annotated tag stores your name, the date, and a message.
    -> This is recommended for most uses.
* EX:-
git tag -a v1.0 -m "version 1.0 release"

# Tag a Specific Commit
    -> You can tag an older commit by specifying its hash:
* EX:-
git tag v1.1 1a2b3c4d
* Replace 1a2b3c4d with the commit hash you want to tag.

# List Tags:-
* See all tags in your repository:
* EX:- 
git tag

# Show Tag Details (git show)
    -> See details about a tag and the commit it points to:
* Ex:-
git show v1.0

# Push Tags to Remote
    -> By default, tags exist only on your local computer.
    -> If you want others to see your tags, you need to push them to your remote 
       repository.
    -> If you don't push your tags, only you will see them, and only locally.
    -> To push a single tag to your remote repository (for example, after creating a 
       release tag):
* EX:-
git push origin v1.0

Note:- 
1. Pushing commits with git push does not push your tags!
2. You must push tags explicitly as shown above.

