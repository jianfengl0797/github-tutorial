# GitHub Tutorial

_by _JianFeng Li_

---
## Git vs. GitHub

_**Git**_ is a local version control system used for creating and saving own
programs. This means that you can check your *history* to control and organize
the files. Git is very useful when you have lots of projects and sub-topics to
work with.  
_**Github**_ is very similar to git where the commands are the same and you code.
However, there are many more benefits in using github. The main benefit is that
github is cloud-based, meaning you can share your program with other programmers
so people can *collaborate* on a project together. It is also a place where you
save your projects for yourself or for the public to see.
</p>

 _Example of the benefit of github:_ Something bad happened to your computer
 and and you lost all your information. Fortunately, you pushed your information
 to github where the information is saved in the cloud. With this benefit, you
 can easily get the project you worked so hard on back.

>Note: Git does not need github, but github needs git to function.

---
## Initial Setup

Creating a github account:
1. Go to github.com and click sign up
2. Enter your personal informations
3. Finish the steps and verify your account

After you finished creating a github account, you need to set up your ide. This
is the place where you type your code and create projects.
Since setting up the ide includes a lot of steps, here's a
[link](https://github.com/hstatsep/ide50) that helps
you set up your working area.

*SSH key* is efficient in github because it allows you to access your account on
github without the requirement of signing in everytime. This key is private and
is only saved on your computer. (Included in the ide setup)
- With the SSH key, you don't need to enter your username and password everytime
when using git commands.

![SSH Key in use](https://help.github.com/assets/images/help/repository/remotes-url.png)

---

## Repository Setup
<ol>
<li> <code> git init </code>

 Everytime you start a new project in a new directory, you'll need to use this command
to connect the file to a github repository. With out initializing, you won't be able
to save your project in the cloud. After you are done initializing, you can start
coding in that directory.
> Note: Never do <code> git init </code> in the main parent directory. If you made this
mistake, do <code> rm -rf .git </code> to undo the mistake.

--
<li> <code> git add (file name) </code> or <code> git add . </code>  --> <code> git commit -m
"(what ever message you want)" </code>

 Now lets say that you are done coding and you want to save your progress. This is where you
do adding and commiting.  
**Adding** is the part where you put your changed file in the staging area,
ready to be committed. You *cannot* commit a change without doing adding first. It's like
trying to take a picture of someone thats in front on the camera versus taking a picture
of someone that's not even in front of the camera.  
**Commiting** is the part where you actually save whatever is on the staging area.
When commiting, it is important to add a message to remind yourself of your progress.
After doing <code> git add </code> and <code> git commit -m </code>

--
<li> <code> git push -u origin master </code>

After you add and commit your changes, you would want to push the changes to github.
You only need to use this code the first time you want to push to a certain repository,
then using <code> git push </code> alone would be enough afterwards. This is because
the -u origin master will remember which branch to push the changes to.

--
<li> If there is nowhere to push your changes to, it means you have to create a new
repository in your github.
 <ol>
  <li> Go to your github
  <li> Press the "+" icon at the top right corner of the page
  <li> Click New Repository
  <li> Create repository name. (Make sure it's exactly the same as the file name)
  <li> <code>git remote add origin "SSH Key"</code> in your ide
  <li> Lastly, do the git push stuff
 </ol>
</ol>


## Workflow & Commands
* git status = Check your status with adding/ committing/ and pushing
* git add = move changes to the staging area
  * git add . = all your changes
  * git add "specific file name" = add certain files to the staging area
* git commit -m "message" = Save the changes that's on the staging area
* git push = push the changes from the ide to a certain repository on github

---
## Rolling Back Changes
 #### How to undo changes*

*Scenerio #1: Made changes in a file but didn't add or commit the change yet*  
Use <code> git checkout "file name" </code> to undo the changes
> Notes Do <code> git status </code> and it will tell you what to do.

*Scenerio #2: Added the changed file by accident*  
Use <code> git reset HEAD </code> to get the file off the staging area.
>Note: This will also be seen in <code> git status </code> when the file name is green

*Scenerio #3: Committed the changed file by accident*  
First, use <code> git reset HEAD~ </code>  
Then, <code> git add </code> the file you want to un-commit  
Lastly, use <code> git status </code> and follow the steps to undo the mistake

