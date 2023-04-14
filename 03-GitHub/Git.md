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
