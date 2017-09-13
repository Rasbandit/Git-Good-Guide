# Git Good Guide
## Setup and Basic Overview
This repo is designed to help teach the workflow of using git in your group project. when using git there are four versions of the code each person should be concerned with. Your personal version or "branch" of code exists in two separate versions; one on your local machine and the other on GitHub. The master branch has the same setup, where there is a version on your local machine and a version on Github. When writing code it is best practice to branch your code and work exclusively on that branch. We will go over how to merge your code into the master branch

### Topics
- [Where do I start?](#Where-do-I-start?)
- [How do I add collaborators?](#How-to-add-contributors)
- [Im a collaborator, now what?](#Im-a-collaborator,-now-what?)
- [What is a branch?](#What-is-a-Branch,-and-why-do-I-need-it.)
- [How do I make a branch?](#Creating-Your-Own-Branch)
- [What branch am I on?](#Checking-What-Branch-You-are-on.)]
- [How do I change branches?](#Getting-on-Your-Branch)
- [How do I merge my code?](#How-Do-I-merge-my-code-with-the-master-Master?)

### Where do I start?
Before you start you will need one person, and only one person, in your group to make the initial repo. Get the whole team together around one computer and decide together how to structure your file tree. You will also want to run create-react-app and install any NPM packages your project will need. an example of a file structure can be seen below.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/files.jpg">

Make sure to create your .gitignore file with node_modules and your .env before you do any add or commits.

When you have the folders in place and the structure you want run git the commands below

<pre>git add .
git commit -m "first commit"
git remote add origin `http://your_git_repo.com`
git push -u origin master</pre>

#### How to add contributors
If you want others to be able to make changes to your code you will need to add them to the repo as a collaborators. To do this click on the settings on the github repo web page.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/settings.jpg">

Once there click on collaborators and you can search for the other team members and send them invitations. Have each user you send the invitation to check their email and they can make pull requests to the master branch (more on what that means).

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/colab.jpg">

#### Im a collaborator, now what?
You won't need to fork the repo before you clone it, if you fork it you make a copy and you wont be working on the same project as the rest of your team. Just clone the repo and make a branch. More on branching below.

### What is a Branch, and why do care?
A branch is when you make a copy of a project but with the intend to make changes but not alter the original version. This will allowing you to make changes to the code with out the risk of breaking the original version.

It also makes it easier for multiple people to work on the same code base and not overwrite or cause conflicts with each other. Then when you are ready to merge your code with the original, git can help make sure everyone's code does not conflict.

### Creating Your Own Branch
To make your own branch run the following command

`git checkout -b [name_of_your_new_branch]`

the -b in the command will make sure you create a branch and switch to it after its creation.

### Checking What Branch You are on.
When starting this guide you will need to be working on your own branch. To check what branch you are on run `git branch`. This will display all the branches you have on your local computer, with a star next to the branch you are working from, or working branch.

<pre>* My_Branch
  master
  Bob_Ross_Branch</pre>

#### Getting on Your Branch
To switch to another branch run the following command

`git checkout [name_of_your_branch]`

**You should never make changes to the code base while on the master Branch**

**Make sure you read the results after you type in every command.**

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-0.jpg" />

## How Do I merge my code with the master Master?

### Step 1: Checkout master

The First Thing we need to do is checkout the master branch. We will be getting the latest version of the master branch on our local machine

**Common Issues**
You can not swap to another branch if you have not done a `git add` and `git commit` to your code. Make sure you read the results after you type in every command.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-1.jpg" />


### Step 2: Pull From master

In Git when we move code around, like uploading or downloading we call it Pushing or Pulling. Both tasks accomplish basically the same thing, but the difference is the direction of the data flow. Here we will be doing a Pull from the master. This command will Pull the code from GitHub and update your local Master version to be identical.

**Never write code while on the master branch or push to the master branch**

**Common Issues**
Sometimes when you try to pull from master it won't let you until you have done an add and commit. This typically means changes were made on your local master branch. Never make changes on the master branch.

To fix this run `git add` and `git commit`. **DO NOT RUN GIT PUSH!!!!** Never push to master.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-2.jpg" />

### Step 3: Switch Back to Your Local branch

When we merge two branches we have to choose what branch will be receiving the changes and which one will be referenced. We want the Master Branch to be the reference and the Personal branch to receive the changes. Because of this, we need to swap back to your Personal Branch.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-3.jpg" />

### Step 4: Merge Your Code with Master

Now that we have a local version of the most up to date Master Branch we can merge our local version with the Master version. While on your local branch run `git merge master`.

**Be sure to read the messages that come after this command to ensure you don't have merge conflicts.**

If you have merge conflicts look at each file it says a conflict has been found (you can ignore your bundle files as those will be fixed after you run Gulp).

Merge conflicts look like this:


<pre>
&#60;&#60;&#60;&#60;&#60;&#60;Head
  var someCode = 'example'
========
  var someOtherCode = 'different example'
&#62;&#62;&#62;&#62;&#62;&#62;Master
</pre>


The part between the `<<<<<<<<Head` and the `=======` is your local version of the code, and the part between the `======` and `>>>>>>>Master` is the code from the master. Talk to whoever the other code belongs to and figure out whose code should be there, make sure you remove the 3 lines that were added when you are done, being the `<<<<<<<<Head`, `=======`, and `>>>>>>>Master`.

**Tip**
If you press `ctrl-shift-f` on windows or `cmd-shift-f` on a mac. You can do a search for every instance of `>>>>>>>Head` in your whole project, making it easier to find conflicts.

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-4.jpg" />

### Step 5: Push Your Code to GitHub

Now that you have merged your code with the Master branch you can push your code up to GitHub. Run `git add .`, `git commit -m "message"`, and `git push`.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-5.jpg" />

### Step 6: Submit A Pull Request

After you push go to your group's repository page on GitHub. A new yellow bar with a green button on the right that says 'Compare & Pull Request' should appear. If fit does not click the New Pull Request button that is highlighted below.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6-1.jpg" />

A new page will load. If you clicked the 'Compare & Pull Request' button then it should look very similar to the image below. Add any comments you would like to make regarding the pull request then click the Green 'Create Pull Request' button in the highlighted 2 section.

If you had to click the gray 'New pull request' button then you will need to click the second gray drop down on the page below. The drop down on the left should read master and the one on the right should read your branch name.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6-2.jpg" />

**Merge conflicts:**
The second page will also inform you if there were any unresolved merge conflicts. If there are then you will need to redo all above steps. Be sure to read all the results from when you run commands. They often tell you exactly what you need to run to resolve the issue.

Once you have submitted your pull request talk to or send a message to your mentor and they will review the pull request and approve it. Once approved the online master branch will have your new code available for the rest of the group.

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-6.jpg" />


### Step 7: Pull Down the New Master code

Checkout the master branch by running `git checkout master` and pull using `git pull`. The rest of your group should do the same. Make sure to switch back to your own branch so you don't make changes to the master.


<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-7.jpg" />
