# Introduction to Git and GitHub

<p align="center">
  <img src="git-logo.png" alt="Git Icon" width="200px">
  
  <h2 align="center">A beginner friendly guide to Git and GitHub.</h1>
</p>

## Table of Contents

* [Introduction](#introduction)
* [What is Git and GitHub?](#what-is-git-and-github)
* [Why use Git and GitHub?](#why-use-git-and-github)
* [Difference between Git and GitHub](#difference-between-git-and-github)
* [Setting up Git](#setting-up-git)
    * [For Windows](#for-windows)
    * [For MacOS](#for-macos)
    * [For Linux](#for-linux)
* [Initializing a Git repository](#initializing-a-git-repository)
* [Basic Structure of Git](#basic-structure-of-git)
    * [The Working Directory](#the-working-directory)
    * [The Staging Area](#the-staging-area)
    * [The Repository](#the-repository)
* [More about the Repository](#more-about-the-repository)
* [The .gitignore file](#the-gitignore-file)
* [Basic Git Commands](#basic-git-commands)
    * [git init](#git-init)
    * [git add](#git-add)
    * [git commit](#git-commit)
    * [git status](#git-status)
    * [git log](#git-log)
    * [git diff](#git-diff)
    * [git branch](#git-branch)
    * [git checkout](#git-checkout)
    * [git merge](#git-merge)
    * [git reset](#git-reset)
    * [git revert](#git-revert)




# Introduction

As CSE grads, We all have to create and manage various projects. Sometimes, the project can be a bunch of files, managing which is simple enough. However, most of the times, we will have to deal with large projects with a lot of files and directories. In such cases, it becomes difficult to manage the project and keep track of all the changes made to the project. This is where Git and GitHub come into play.<br>
# What is Git and GitHub?

<b>Formally speaking,</b> Git is is a `distributed version-control system` for tracking changes in source code during software development. It is designed for coordinating work among programmers, but it can be used to track changes in any set of files. GitHub, on the other hand, is a `web-based Git repository hosting service`. It offers all of the distributed version control and source code management functionality of Git as well as adding its own features.<br>
<b>In layman's terms,</b> Git is a tool that helps you keep track of changes made to your project files and GitHub is a platform where you can store your project files and collaborate with others.<br>

# Why use Git and GitHub?

Say you are working on a project and need to do some experimantation, maybe test a new cool idea you have just thought of. However, there is a good chance that this will break the existing code. So, you `initialize a git repository` in the project folder. <br>
<b>Git</b> allows to create cretain `checkpoints` in the project, which will save all filesin the project `at that point of time`. This is called a `commit`. So, you can make changes to the project, and if you break something, you can always go back to the last commit and start over. <br> 
Not only that, you can also create `branches` in the project, which are like different versions of the project. You can work on a new feature in a branch, and if it works, you can `merge` the branch with the main project. If it doesn't work, you can simply delete the branch. <br>

# Difference between Git and GitHub

You have created some awesome projects on your own. But now, you want to build something with your friends. You can't just copy the project files to their computer, make changes and copy them back. This is where `GitHub` comes in. <br>
Github is basically a `cloud storage` for your project files. It is built upon `Git`, so you can use all the features of `Git` in `GitHub`. You can `push` your project files to `GitHub`, and your friends can `pull` the files from `GitHub` to their computer. They can make changes, and `push` the files back to `GitHub`. You can `pull` the changes to your computer. This way, you can collaborate with your friends on a project. They can create their own separate branches, and you can `merge` them with the main project. <br>

<b>For this lesson, we will be learning the basics of `Git`.</b>

# Setting up Git

Before you can start using Git, you need to set it up on your computer. Here is how you can do it:<br>


## For Windows

1. Download the latest version of Git from [here](https://git-scm.com/download/win).
2. Before running the downloaded file, you can install an `IDE` like `VS Code` which you can download from [here](https://code.visualstudio.com/download).
3. Run the downloaded file and follow the instructions in the installer. WHen asked to `Select a default editor`, you can select `Visual Studio Code` if you have installed it. Otherwise, just select `Vim`.
4. Afterwords, selecting the default options is just fine.

Installing Git on Windows algo gives you a Unix-style terminal that you can use to run Git commands. This is the `Git Bash` terminal. You can open it by searching for `Git Bash` in the start menu. Or you cal totally use the `Command Prompt` or `PowerShell` to run Git commands. Just be sure to close and repoen the terminal after installing Git, if you had it open before installing Git.

## For MacOS

1. Download the latest version of Git from [here](https://git-scm.com/download/mac).
2. Run the downloaded file and follow the instructions in the installer.

Installing Git on MacOS also gives you a Unix-style terminal that you can use to run Git commands. This is the `Terminal` app. You can open it by searching for `Terminal` in the spotlight search.

## For Linux

1. You can install Git using the package manager of your Linux distribution. For Ubuntu or any Debian based distros, you can run the following command in the terminal:

    ```bash
    sudo apt update
    sudo apt install git
    ```

2. For Fedora or any Red Hat based distros, you can run the following command in the terminal:

    ```bash
    sudo dnf install git
    ```

After installing Git, you can open the terminal and run the following command to check if Git has been installed successfully.

```bash
git --version
```

For Git to work, we first need to configure our username and email address. We can do this by running the following commands in the terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "
```

the `--global` flag is used to set the configuration globally, so you don't have to set it again for other repositories.

# Initializing a Git repository

To start using Git in a project, you need to initialize a Git repository in the project folder. You can do this by opening a terminal in your project folder and running the following command in the terminal:

```bash
git init
```

This will create a hidden folder called `.git` in the project folder. This folder contains all the information about the project, like the commits, branches, etc.
If you delete this folder, you will lose all the information about the project. So, be careful with this folder.

# Basic Structure of Git

There are three main parts of a Git project:

* <b>The Working Directory</b>
* <b>The Staging Area</b>
* <b>The Repository</b>

## The Working Directory

The `working directory` of the `Workdir` is the folder where you are working on the project. It contains all the files and directories of the project. When you open the project folder in an editor, you are working in the working directory. This is where you make changes to the project files.

## The Staging Area

The `staging area` or the `Index` is like a `checkpoint` in the project. You can `add` files to the staging area, and when you are happy with the changes, you can `commit` the changes to the repository. This is like saving the changes in the project.

## The Repository

The `repository` or the `Repo` is where all the information about the project is stored. It contains all the commits, branches, etc. When you `commit` changes to the repository, you are saving the changes in the project. These `commits` are like little time capsules that store the state of the project at that point of time.

# More about the Repository

The `repository` is stored in a hidden folder called `.git` in the project folder. This folder contains all the information about the project, like the commits, branches, etc. If you delete this folder, you will lose all the information about the project. So, be careful with this folder.




