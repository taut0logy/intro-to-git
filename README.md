# Introduction to Git and GitHub

<p align="center">
  <img src="git-logo.png" alt="Git Icon" width="200px">
  
  <h2 align="center">A beginner friendly guide to Git</h1>
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
    * [The special `HEAD` file](#the-special-head-file)
    * [git diff](#git-diff)
    * [git restore](#git-restore)
    * [git reset](#git-reset)
    * [git branch](#git-branch)
    * [git checkout](#git-checkout)
    * [git merge](#git-merge)
    * [Merge Conflicts](#merge-conflicts)
    * [git amend](#git-amend)
    * [git revert](#git-revert)
* [Conclusion](#conclusion)
* [Useful Resources](#useful-resources)




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

# The .gitignore file

Sometimes there are files and folders we don't want to manage with Git. For example, the `node_modules` folder in a Node.js project. We don't want to manage this folder with Git because it contains a lot of files and folders that are not necessary for the project. We can tell Git to ignore this folder by creating a file called `.gitignore` in the project folder. This file contains a list of files and folders that Git should ignore. Here is an example of a `.gitignore` file:

```
node_modules/
.DS_Store
```

This file tells Git to ignore the `node_modules` folder and the `.DS_Store` file. You can add more files and folders to this file as needed. Note that the folder name ends with a `/` and the file name does not.

<b>Now that we've clared up the basics, let's move on to some basic Git commands.</b>

Suppose, you have a project folder called `my-project`. You want to use Git to maange it. We will be referencing this project folder while explaining the commands.

# Basic Git Commands

## git init

The `git init` command is used to initialize a Git repository in the project folder. You can run this command in the terminal in the project folder to create a new Git repository.



```bash
git init
```

This will create a hidden folder called `.git` in the project folder. This folder contains all the information about the project, like the commits, branches, etc.

## git add

First, let's create a new file called `index.txt' in the project folder. Let's write something in it.
### index.txt
```txt
```bash
Hello, World!
```
Let's add this file to the staging area. You can do this by running the following command in the terminal:

```bash
git add index.txt
```

This will add the current state of the `index.txt` file to the staging area. You can also add all the files in the project folder to the staging area by running the following command in the terminal:

```bash
git add .
```

This will add all the files in the project folder to the staging area.

## git commit

Now that we have added the `index.txt` file to the staging area, we can commit the changes to the repository. You can do this by running the following command in the terminal:

```bash
git commit -m "Initial commit"
```

The `commit` commnd will permanently save the files in the staging area in thir current states, which you can revisit and revert to at any time. Since it is a <b>Save Point</b>, it needs a message to document the changes made. It is a good practice to add a detailed message to the commit, so you can remember what changes you made in the commit. You can do this by adding the `-m` flag followed by the message in quotes.

## git status

Since we have made our first commit, let's see the current status of the repository. Use the following command in the terminal:

```bash
git status
```

The output should be something like this:

```bash
On branch master
nothing to commit, working tree clean
```

This will show you the current status of the repository. It will show you the current branch, the files in the working directory, the files in the staging area, and the files in the repository.

Let's make some changes in the `index.txt` file and see how the status changes. Add the following line to the `index.txt` file:


```bash
Hello, KUET!
```
Runnig the `git status` command again will show the following output:

```bash
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   index.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
We can see that the `index.txt` file has been modified, but the changes have not yet been staged. Let's add the changes to the staging area and run the `git status` command again:

```bash
git add index.txt
git status
```

The output should be something like this:

```bash
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   index.txt
```

We can see that the `index.txt` file has been added to the staging area and is ready to be committed. Let's commit the changes.

```bash
git commit -m "Update index.txt"
```

The output should be something like this:

```bash
[master 45c661a] Update index.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
```

The changes have been committed to the repository. You can run the `git status` command again to see the current status of the repository.

## git log

Now that we have made some commits, let's see the commit history of the repository. You can do this by running the following command in the terminal:

```bash
git log
```

The output should be something like this:

```bash
commit 45c661adf65b710f0782d47192a6fabb9741d8e5 (HEAD -> master)
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:18:04 2024 +0600

    Update index.txt

commit 2517404e213f4d39b6ec776deda7966b65269dea
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:17:03 2024 +0600

    Initial commit
```

Here we can see the list of commits, each with a unique identifier called a `SHA`, the author of the commit, the date and time of the commit, and the commit message.<br>

Notice that on the very last commit, there is a `HEAD -> master` tag. This indicates that the `HEAD` is currently pointing to the `master` branch. Let's talk about the `HEAD`.

## The special `HEAD` file

There is a file called `HEAD` in the `.git` folder. This file contains the `SHA` of the last commit in the repository. The `HEAD` is like a pointer that points to the current commit in the repository. When you make a new commit, the `HEAD` is updated to point to the new commit. The position of the `HEAD` determines the current state of the repository.

<p align="center"><img src="git-head.webp" width="600px"/></p>

## git diff

Now, let's make some more changes to the repository. Let's add a new file called `about.txt` to the project folder. Add the following content to the `about.txt` file:

### about.txt
```txt
I am Raufun
```
Let's stage our changes.

```bash
git add about.txt
```

Now, let's make some changes to the `about.txt` file. Add the following line to the `index.txt` file:

```bash
I am raufun
I am a KUETian.
```
Now, let's see the changes we made to the `about.txt` file. You can do this by running the following command in the terminal:

```bash
git diff
```

The output should be something like this:

```bash
diff --git a/about.txt b/about.txt
index 7041275..49d4f70 100644
--- a/about.txt
+++ b/about.txt
@@ -1 +1,2 @@
 I am Raufun.
+I am a KUETian.
```

The `git diff` shows you the changes you made in your projct since you last staged it. The `+` sign indicates the lines that have been added, and the `-` sign indicates the lines that have been removed.

## git restore

Now, let's say you made some changes to the `about.txt` file, but you want to discard the changes and go back to the last staged state. You can do this by running the following command in the terminal:

```bash
git restore about.txt
```

Now the contents of the `about.txt` file will be :

### about.txt

```bash
I am Raufun.
```

Remember, `git restore` will discard any unstaged changes and restore the file to the last staging. It will also remove the file from the staging area. Running `git status` will show the following output:

```bash
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	about.txt

nothing added to commit but untracked files present (use "git add" to track)
```

If you want to discard the changes and keep the file staged, you can use the `--staged` flag:

```bash
git restore --staged about.txt
```

## git reset

The `git reset --hard` command will discard all changes made to the project since the last commit. This includes all staged and unstaged changes. You can do this by running the following command in the terminal:

```bash
git reset --hard HEAD
```

This will show the following output:

```bash
HEAD is now at 45c661a Update index.txt
```

Running `git status` will show the following output:

```bash
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	about.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Since `about.txt` was not staged, it was not affected by the `git reset --hard` command.

Now can stage and commit the changes if you want to.

## git branch

Now, we want to try out a new feature, but we don't want to mess up the main project. To solve this, we can create a new `branch`. A branch is like a separate version of the project where you can work on new features without affecting the main project. In git, the default branch is called `master`.<br/>
You can create a new branch by running the following command in the terminal:

```bash
git branch new-feature
```

This will create a new branch called `new-feature`. You can switch to the new branch by running the following command in the terminal:

```bash
git checkout new-feature
```

output:
```bash
Switched to branch 'new-feature'
```

Now, you are in the `new-feature` branch. You can make changes to the project without affecting the main project. Let's create a new file called `feature.txt` in the project folder. Add the following content to the `feature.txt` file:

### feature.txt
```txt
This is an awesome new feature!
```

Let's stage the changes and commit them to the `new-feature` branch.

```bash
git add .
git commit -m "Add new feature"
```

This will stage all changes and commit them right away.

Now, if we run the `git log` command, we will see the following output:

```bash
commit d3c7a646bb40ccc7d17e8094a44ed138a35e9f03 (HEAD -> new-feature)
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:46:22 2024 +0600

    Add new feature

commit 8a32bdb2280acc216f34c9e9e263676211a0bb27 (master)
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:44:50 2024 +0600

    Added about.txt

commit 45c661adf65b710f0782d47192a6fabb9741d8e5
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:18:04 2024 +0600

    Update index.txt

commit 2517404e213f4d39b6ec776deda7966b65269dea
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:17:03 2024 +0600

    Initial commit
```

Notice that the `HEAD` is now pointing to the `new-feature` branch. This is because we are currently in the `new-feature` branch.

## git checkout

Now, let's say we want to switch back to the `master` branch. You can do this by running the following command in the terminal:

```bash
git checkout master
```

output:
```bash
Switched to branch 'master'
```

Now, run `git log`.

```bash
commit 8a32bdb2280acc216f34c9e9e263676211a0bb27 (HEAD -> master)
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:44:50 2024 +0600

    Added about.txt

commit 45c661adf65b710f0782d47192a6fabb9741d8e5
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:18:04 2024 +0600

    Update index.txt

commit 2517404e213f4d39b6ec776deda7966b65269dea
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:17:03 2024 +0600

    Initial commit
```
We can see that the `HEAD` is now pointing to the `master` branch.

## git merge

Now, let's say we are happy with the changes in the `new-feature` branch and want to include them in the main project. We can do this by <b>merging</b> the `new-feature` branch with the `master` branch. You can do this by running the following command in the terminal:

```bash
git merge new-feature
```

output:

```bash
Updating 8a32bdb..d3c7a64
Fast-forward
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

We can see that the changes in the `new-feature` branch have been merged with the `master` branch. If we run the `git log` command, we will see the following output:

```bash
commit d3c7a646bb40ccc7d17e8094a44ed138a35e9f03 (HEAD -> master, new-feature)
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:46:22 2024 +0600

    Add new feature

commit 8a32bdb2280acc216f34c9e9e263676211a0bb27
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:44:50 2024 +0600

    Added about.txt

commit 45c661adf65b710f0782d47192a6fabb9741d8e5
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:18:04 2024 +0600

    Update index.txt

commit 2517404e213f4d39b6ec776deda7966b65269dea
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 22:17:03 2024 +0600

    Initial commit
```

The branches have been merged, and their respective commits are interwoven. The `HEAD` is now pointing to the `master` branch.

## Merge Conflicts

Now, let's work on a new feature. Create a new branch called `new-feature-2` and switch to it.

```bash
git checkout -b new-feature-2
```

This will create a new branch called `new-feature-2` and switch to it. Now, to make this feature work, we need to make some changes to the `index.txt` file. The changes are as follows:

### index.txt at new-feature-2

```bash
Hello, KUET CSE!
```

Commit the changes.

```bash
git commit -am "Update index.txt on new feature 2 branch"
```

The flag `-am` is a shorthand for `git add .` and `git commit -m`. It stages all changes to <b>tracked</b> files and commits them right away.

Now, you suddenly realize that you need to make changes to the `index.txt` file in the `master` branch. Switch back to the `master` branch.

```bash
git checkout master
```

Now, make some changes to the `index.txt` file in the `master` branch. The changes are as follows:

### index.txt at master
```bash
Hello, KUET!
Hello, CSE 2K23!
```

Commit the changes.

```bash
git commit -am "Update index.txt on master branch"
```

Now, let's try to merge the `new-feature-2` branch with the `master` branch.

```bash
git merge new-feature-2
```

output:

```bash
Auto-merging index.txt
CONFLICT (content): Merge conflict in index.txt
Automatic merge failed; fix conflicts and then commit the result.
```
This phenomenon is called a `merge conflict`. A merge conflict occurs when Git is unable to automatically merge the changes made in two branches. In this case, the changes made in the `index.txt` file in the `master` branch and the `new-feature-2` branch conflict with each other. Git is unable to determine which changes to keep, so it asks you to resolve the conflict manually.

Open the `index.txt` file in your editor. You will see something like this:

```bash
<<<<<<< HEAD
Hello, KUET!
Hello, CSE 2K23!
=======
Hello, KUET CSE!
>>>>>>> new-feature-2
```

The `<<<<<<< HEAD`, `=======`, and `>>>>>>> new-feature-2` lines indicate the conflicting changes. The changes between `<<<<<<< HEAD` and `=======` are the changes made in the `master` branch, and the changes between `=======` and `>>>>>>> new-feature-2` are the changes made in the `new-feature-2` branch. Here, the changes made outside the current branch are called `incoming changes`. The changes made in the current branch are called `current changes`.<br>

You need to decide which changes to keep and which changes to discard. In this case, let's keep both changes. The resolved `index.txt` file should look like this:

### index.txt after resolving the conflict

```bash
Hello KUET!
Hello, CSE 2K23!
Hello, KUET CSE!
```

Now, stage the resolved file and commit the changes.

```bash
git add .
git commit -m "Resolve merge conflict"
```
Running `git log`, the latest commit will be something like this:

```bash
commit 6c3e98cda90845d396b464eab32f8a60908c7e99 (HEAD -> master)
Merge: 6eda82f 0635700
Author: taut0logy <raufun.ahsan@gmail.com>
Date:   Wed Oct 30 23:41:25 2024 +0600

    Resolve merge conflict
```

The merge conflict has been resolved, and the branches have been merged successfully.

## git revert

Now, let's say you made a commit that you want to undo. You can do this by running the following command in the terminal:

```bash
git revert HEAD
```

This will create a new commit that undoes the changes made in the last commit. You can also specify a specific commit to revert by using the `SHA` of the commit. You can find the `SHA` of the commit by running the `git log` command.

```bash
git revert 6c3e98cda90845d396b464eab32f8a60908c7e99
```

This will create a new commit that undoes the changes made in the specified commit.

# git amend

Now, let's say you made a commit, but you forgot to add a file to the commit. You can do this by running the following command in the terminal:

```bash
git add forgotten-file.txt
git commit --amend
```

This will add the `forgotten-file.txt` file to the last commit. You can also change the commit message by adding the `-m` flag followed by the new message in quotes.

```bash
git commit --amend -m "Add forgotten-file.txt"
```

amend essentially allows you to add changes to the last commit without creating a new commit.

# Conclusion

This guide is meant for absolute beginners requiring no prior knowledge about version control systems. The commands used here are only the basic ones, Git offers a lot more functionalities for advances and professional users. In order to be good developer, a clear knowledge o git is a must. So, keep practicing and exploring the world of Git and GitHub. Happy coding! 

# Useful Resources

* [Git Documentation](https://git-scm.com/doc)
* [GitHub Guides](https://guides.github.com/)
* [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
* [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)