# Ultimate Guide to GIT for Ubuntu
## Created by Jennifer Grisales
## Creado el 30 de agosto de 2023
## Mod 31 agosto 2023
### This file uses markdown. References appears throughout the document.
### Waring: If you follow each command lines you will succeed. Please don't get so creative.

1) Instalation: In your terminal...
   
> sudo apt install git-all -y

2) Prove the instalation:
   
> mkdir prueba

> cd prueba

> git init

You'll obtain a message like: 

> "Inicializado repositorio Git vacío en /home/jennifer/Documentos/prueba/.git/"

Whit **git init** you'll tell to git that this folder will be a local repo. You should use this command on any folder that works as a repository, each time that you work there.

3) Synchronize git with github: (*if you follow each command lines you will succeed. Don't get creative.*)
 Github is only one framework that uses git to manage online versions of your work. The main of this guide is to be able to use git locally (more convenient) via terminal and at the same time ensure a secure and easy cloud backup. So, before start using local git, before using the local git, let's do this synchronization:

*Using SSH security protocol just because I like it* fuente: https://ubc-library-rc.github.io/intro-git/content/03_sync.html

> ssh-keygen -t rsa -C "email_adress@domain.xx" (email address registered in github)

The following information is requested on the screen, follow the indications below:
> Enter file in which to save the key (/home/jennifer/.ssh/id_rsa): CLICK ENTER FOR DEFAULT FILE
> Enter passphrase (empty for no passphrase): CLICK ENTER FOR SKIP (don't mess with that)
> Enter same passphrase again: CLICK ENTER OBVIOUSLY

Will be displayed like this:
> Your identification has been saved in /home/jennifer/.ssh/id_rsa
Your public key has been saved in /home/jennifer/.ssh/id_rsa.pub
The key fingerprint is:

**A character block appears here**

> SHA256:SMSPIStNyA00KPxuYu94KpZgRAYjgt9g4BA4kFy3g1o yourname@domain.name
The key's randomart image is:
> +--[ED25519 256]--+
|^B== o.          |
|%*=.*.+          |
|+=.E =.+         |
| .=.+.o..        |
|....  . S        |
|.+ o             |
|+ =              |
|.o.o             |
|oo+.             |
+----[SHA256]-----+
> $

Keep this shit somewhere... and dont share it with anyone...

Now, show the key on the terminal like this:
> cat ~/.ssh/id_rsa.pub

Copy the entire output please.

**ALERT!!! The next steps are to be performed on the official github website** (I'll try explain this for really dummies sorry)

- log in to https://github.com
- Go to the top right, to the profile icon and click on it...
- Click _settings_
- Then look at the left sidebar that will appear and select the option: _SSH and GPG keys_
- Click on the _New SSH key_ button.
- Three spaces appear: title, key type and key. Fill them as follows:

Title: (A simple reference name for the computer with the key example: _Jenn-Lenovo-0823_)
Key type: Authentication key}
Key: (Paste into the box the characters from the output you copied from the terminal without adding any spaces)

- Ok, click on _Add SSH Key_ button

(And that's it!!! Looks easy JAJAJA it's worth this shit, believe me)

**Ok babe, return to the beautiful terminal...** (Just kidding, there are still a few things missing.)

Type:
> ssh -T git@github.com

The output is:

>Hi username_github! You've successfully authenticated, but GitHub does not provide shell access.

**may happen...** This thing could appear:
>The authenticity of host 'github.com (140.82.113.4)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])?

ANSWER: yes
Then, the output will be:
> Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi jennifergc! You've successfully authenticated, but GitHub does not provide shell access.
>

**FINALLY Type:**
> git config --global user.email "you@example.com"

> git config --global user.name "Tu Nombre"

**WE DID IT!!!!!**

4) Using GIT and GITHUB with superpowers

We need understand the mechanism/protocol of git: 

- Whit a git folder you'll start a TREE. Each tree has a BRANCH. The initial BRANCH state of the repo has the name MASTER. For do that we always type:
  > git init
- If you want to have very alternative versions of a proyect you should have other BRANCHES obviously at the same level of MASTER.
- You need to tell git which branch you'll use. For starting in this world we'll ignore this posibility and for now will always work in the MASTER branch.
- When you make changes to the repository you can identify a state of the work that maybe should be saved if something gets damaged later on. For make that, git stablish three levels of working:
Level 1: **Working directory** (Unsaved data)
> git status

With _git status_ let you know know which files are being modified.

Level 2: **Staging area** (Identified changes) typing:
> git add

You should add for the staging area an specific file like this:
> git add <file>

For everything:
> git add -A

Level 3: **Git repository** (Saved version of the folder) typing:
> git commit -m "commit message"

- The important thing about this step, is that you can create one (or many) new branches from a given commit, for that it sets a flag for each commit.
- After committing your changes, the next thing you want to do is send your changes to the remote server.
> git push -u origin <branch_name>

- Before start working on the local repo, you always may update your repo from the local server. Like this:
> git pull

5) LIFE HACK FOR USE THE CLOUD - LOCAL SYNC

Really I don't know how to made it different... so, MY WAY IS first create the repo on GITHUB and CLONE the repo in my LAPTOP
(if you find another way, let me know). Follow the steps:

- Ok, go to Github, click on _repositories_ and click on _New_
- Write a name (don't use spaces)
- Write a description (optional)
- Define the visibility for others
- Add the README file (Ok all the repos should have this shit please)
- Keep the other things unchanged
- Click on _Create repository_
- Copy the SSH link

Let's go to CLONE this on our local server:

- Go to the terminal
- Type on the local repo folder:
  > git clone SSH link
- Now you have a new folder in your directory.

**WE DID IT!!!!!**
Now you can use the basic comand lines for sync the local repo with GITHUB.

**You're welcome**

