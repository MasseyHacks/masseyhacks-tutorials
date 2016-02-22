# Working with git and GitHub

## What is git? Why does it have a Hub?

Have you ever thought about programming on a team? How will you all work on the same code without messing each other up? How will you keep the same code updated amongst everyone on the team?

Git was invented for this purpose. It's a program that controls your code, especially for working in a team. GitHub is a website (the one that you're on right now) which gives free hosting space for code projects that use git -- provided that you're okay with other people seeing your code.

If you plan to do any coding with your friends or coworkers, in the industry or just for fun, you'll probably end up using git. So it's pretty important that you learn to use it.

## Getting Ready

1. You're going to need a GitHub account. Register one by pressing the big green "Sign Up" on the top right. 
2. Get yourself a copy of git on your computer. You've got two choices:
	- Regular Git: Requires knowledge of the command line. If you're comfortable with a terminal, we'd definitely recommend this one. If you've got a package manager, you're welcome to get git from there.
		- [Download Git for Windows](https://git-for-windows.github.io/)
		- [Download Git for OSX](https://code.google.com/archive/p/git-osx-installer/downloads)
		- [Download Git for Linux](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
	- GitHub Desktop: A friendly GUI version for those who don't know how to use a command line.
		- [Download GitHub Desktop for Windows/OSX](https://desktop.github.com/)
		- Linux not supported, sorry. If you're a Linux user, chances are you're downloading regular command line git right now.

## Step 1: Making a Repository

A **repository**, or repo for short, is the space where your code project goes. It doesn't have to be just code -- it could be word documents, images, whatever you'd like in your code project! All of your friends will be working on this one repository.

We're going back to a classic for this one: Hello World! But first, a note: you're technically going to have two repositories: a local one on your computer, managed with git, and the online one, managed with GitHub. Don't concern yourself with specifics right now, let's get to work.

#### Creating a Repository on GitHub

Let's get the online repository up and running first. Head over to your web browser and get on GitHub.

1. In the upper right corner, next to your username, click the **+** and then click **New repository**.
2. Name your repository `hello-world`.
3. Write a short description, if you'd like.
4. Select **Initialize this repository with a README**.
5. You're ready! Click the big green `Create repository` button.

<p align="center"><img src="resources/github-new-repo-screen.png"/></p>

#### Creating a Repository on git

Now you're going to have to make a local repo on your computer, and this one will be handled by git.

- Terminal Users:
	1. Navigate or create a directory that you'd like to keep your `hello-world` project in. While within the directory, call `git init`. This command will automagically set up the directory for use with git.
	2. Now tell git that the GitHub repo exists. Back at GitHub, make your way to the `hello-world` repo page, and copy the link that's given in the top toolbar. This is a link to this GitHub repo. I've selected the link in orange for you so you can find it quickly.
		<p align="center"><img src="resources/github-repo-page-link-selected-scaled.png"/></p>
	3. Back in the terminal, call the command `git remote add origin <link to repo>`. This tells the local git repo about the online GitHub repository.
	4. Now let's get the two repositories in sync. The online repo has a `README.md` file. Clone it on the local repo by calling `git pull origin master`. Don't bother with `origin` or `master` for now.
- Desktop Users:
	1. Unlike terminal users, you don't need to make a local repo. GitHub Desktop does it automatically for you. *Sign in*
	
#### Why do we have two repositories?

Remember: Git and GitHub are two different programs. There will be a central official repository online, hosted by GitHub. However, you should perform the changes that you want to make on the project on your local git repository, and then tell git to make those same changes on the official GitHub repo.

This might seem tedious if you're working alone, but think about what happens in a team. It would be pretty chaotic if everyone made their own direct changes on the official online repository. If everyone had their own little local version of the official repository, they could use git to keep changes constant between everyone's local repositories and the official online repo.

#### Something to notice: README's are actually read.

GitHub repos search for a file called `README.whatever` and display it on the repo web page. This way, `README`'s are actually read and not absolutely ignored.

When you were creating your `hello-world` repo, you opted for a `README` to be created for you. If you look at your webpage right now, you can see it in action as a giant box under the list of files in your repo, along with the description that you gave to the repo.

<p align="center"><img src="resources/github-readme.png" /></p>

GitHub also supports Markdown editing with `README`'s. Normally, the filename is `README.md`. If you don't know what Markdown is, don't worry. Just treat the `README` as a regular text file.

## Step 2: Add, Commit, Push.

Say you make a change to your local repo. Open up your favourite text editor (bonus points if it's Vim) and create a new text file in the repo. It can be anything you want, and you can put whatever you'd like in it.

<p align="center"><img src="resources/github-wowow.gif" alt="wowowowowwowowowowowowow"/></p>

This new file is going to represent a change to your code project. Now, lets get this change from your local git repo to the online official GitHub repo.

#### Adding a File:

Git doesn't recognise new files unless you want it to. First, you'll need to tell Git that the file exists. If you haven't made a new file, however, you can skip directly to **Committing a Change**.

- Terminal Users:
	1. Use the command `git add` to add the file. There are lots of options to choose from:
		- `git add <filename>`: Adds the given file and nothing else.
		- `git add *`: Adds all the files in the current directory.
		- `git add .`: Adds all the files in the current directory recursively. That means that, for a folder that is sitting within your directory, all the files and folders within that folder will be added too.
- Desktop Users:

#### Committing a Change:

Now you're going to have to tell Git that you've made changes to the local repo.
