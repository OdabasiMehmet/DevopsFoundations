Git is a DevOps tool for source code management. In order to use version control systems, you need to install Git on your system. Then you will need to use git commands to manage your files. In the following part, you can find the installation guides followed by basic git commands.

# Installation

## Installing on Windows

1. Download the latest version of Git from Git Website : https://git-scm.com/downloads. Then install it on your system.

2. If you have winget installed, you can also install Git with the following command:

```bash
 winget install --id Git.Git -e --source winget
 ```

## Installing on Linux

Depending on you system use a packet manager to install Git

```bash
sudo yum install git 
sudo apt-get install git
```

## Installing on Mac

```bash
brew install git
```

# Basic Git Commands

## Identity and Editor
When you install Git on your system, it is important that you set up your identity. Therefore, when you make a commit, the system will know that it came from you.

```bash
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

You can also set up a default editor

```bash
git config --global core.editor nano
```
## Default branch 

By default Git will create a branch called master when you create a new repository with git init. If you want to use main instead of master, then run the following command.

```bash
git config --global init.defaultBranch main
```

## Configuration

If you want to see a list of your configuration, such as the user and user email, then run the following command

```bash
git config --list
```

## How to get Help

Just run `git help`to get help about git.

You can also get help on a specific command such as `git help config`

## Initializing a Repository

While working locally, there are two ways to use a folder as a Git Repo. 
1. You create a new directory (folder) to work on and turn that new directory into a local repo.

```bash
mkdir mynewfolder
cd mynewfolder
git init
```

When you run `git init`command, Git will create a .git hidden folder that contains all of your necessary repository files.

2. Clone an existing repository

You may have access to an existing Git repository (either any public repo on Github or a project that you work with your team members)

```bash
git clone https://github.com/repoaddress
```
Then simply cd into that directory

## Making Changes and Keeping track of the Changes

You can add a new file or modify an existing file in your Git repository. If you want to see if there have been any changes in your Git repository, you can run the status command.

```bash
git status
``` 

Imagine that you have worked on some files and saved them. They will be seen as unttacked changes in the git status. In order to add them to staging area, you should use git add command.

```bash
git add .
```

Note the . at the end of the command denoting the current directory. In other words, it lets the system know where to find the files that will be added to the staging area.

Also know that you can specify the file to be added to staging area by name since we are working in the same directory. But having the dot removes the necessity to write down the names of each individual files and simply add all modified files in the working directory.

Once the files are added, they are ready to be committed. By committing, what we do is actually take a snapshot of the current state of the files, just like doing a save as operation in a word document. While doing a commit, we also add a message that explains the nature of the commit.

```bash
git commit -m "Python code modified"
```

## Branches and Merging

When working with git, we use branches to isolate our work from the main branch or the other branches. Think of each branch as a seperate person working on the same set of files. When you create a branch from the main branch, or let's say main original file, what you do is actually cloning the main file and using an isolated version of it. Therefore, when you work in a specific branch, the main branch stays intact until we decide to merge the new branch into the main branch.

To see a list of current branches we use git branch command.

```bash
git branch
```

To see the remote branches, we can use the -r flag, and to see all local and remote branches we can use the -a flag along with the git branch command.

```bash
git branch -r
git branch -a
```

To create a new branch we simply provide a name after git branch command

```bash
git branch mynewbranch
```

If you want to use that branch, then you need to swicth to that branch. We use git checkout command to wsith to a new branch

```bash
git checkout mynewbranch
```

There is actually a shortcut to this operation. Instead of first creating the branch and then checkout to that brahc, we use git checkout command with -b flag which creates and switches to a new branch.

```bash
git checkout -b newbranch
```
To delete a branch, we use the -d flag (Capital D to delete it forcefully)

```bash
git branch -d mynewbranch
```