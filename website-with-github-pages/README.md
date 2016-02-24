# Building a Website with GitHub Pages

## Websites on GitHub?!

For each GitHub account, you'll be able to host a website at `<username>.github.io` for free, as long as you're willing to share the code within that website as a GitHub repo (or, if you're not comfortable with that, buy a private repo for your website). Each organisation and project can also get a place on `github.io`. This service is called GitHub Pages.

This workshop will focus on two things. First, it will teach you how to make a simple website out of HTML/CSS. Secondly, it will teach you how to host that website on GitHub. This workshop is not intended to be a through guide to both, and is targeted to people who have little to no experience at both.

## Step 0: Prerequisites
1. You're going to need to know how to use git with GitHub. I'd recommend going through our [Git and GitHub Tutorial](git-and-github) by attending the workshop during the hackathon! The rest of these prerequisites is just a copy of the things you need for that workshop.
2. You're going to need a GitHub account. Register one by pressing the big green "Sign Up" on the top right. 
3. Get yourself a copy of git on your computer. You've got two choices:
	- Regular Git: Requires knowledge of the command line. If you're comfortable with a terminal, we'd definitely recommend this one. If you've got a package manager, you're welcome to get git from there.
		- [Download Git for Windows](https://git-for-windows.github.io/)
		- [Download Git for OSX](https://code.google.com/archive/p/git-osx-installer/downloads)
		- [Download Git for Linux](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
	- GitHub Desktop: A friendly GUI version for those who don't know how to use a command line.
		- [Download GitHub Desktop for Windows/OSX](https://desktop.github.com/)
		- Linux not supported, sorry. If you're a Linux user, chances are you're downloading regular command line git right now.

## Step 1: Creating the Repository

GitHub Pages operates out of a GitHub repository. Go to the new repository creation screen and create a repository called `<username>.github.io`, where `<username>` is your GitHub username. It is important that you name the repo in this EXACT format, or GitHub will not identify it for GitHub Pages.

<p align="center"><img src="resources/pages-create-repo.png"/></p>
