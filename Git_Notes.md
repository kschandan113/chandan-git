

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
