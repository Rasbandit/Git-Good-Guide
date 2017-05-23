# Git Good Guide
## Setup and Basic Overview
This repo is designed to help teach the work flow of using git in your group project. when using git there are essentially four versions of the code base to be concered with. Your branch of code exists in two seperate versions, one on your local machine and the other on GitHub. The master branch has the same setup, where there is a version on your local machine and a version on Github. Git is designed for you to work on the code in your own branch without causing issues in others code.

#### What is a Branch, and why do I need it.
A branch is when you take an existing code base and make a copy of the code. This copy will not effect the original or 'Master' branch, allowing you to make changes to the code with out the risk of causing issues in the original code.

It also makes it easier for multiple people to work on the same code base and not overwrite or cause conflicts in each others code. Then when you are ready to merge your code with the original code git can help make sure every one's code does not overwrite each other.

#### Creating Your Own Branch
To make your own branch run the following command
`git checkout -b [name_of_your_new_branch]`
the -b in the command will make sure you create a branch and switch to it after its creation

#### Checking What Branch You are on.
When starting this guide you will need to be working on your own branch. To check what branch you are on run `git branch`. This will display all the branches you have on your local computer, with a star next to the branch you are working from, or working branch.

<pre>* My_Branch
  master
  Bob_Ross_Branch</pre>

#### Getting on Your Branch
To switch to another branch run the following command
`git checkout [name_of_your_branch]`

**You should never make changes to the code base while on the master Branch**

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-0.jpg" />


### Step 1: Checkout master

The First Thing we need to do is checkout the master branch. We will be getting the latest version of the master branch on our local machine

<img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-1.jpg" />


### Step 2: Pull From master

In Git when we move code around, like uploading or downloading we call it Pushing or Pulling. Both tasks acomplish basically the same thing, but the difference is the direction of the data flow. Here we will be doing a Pull from the master. This command will Pull the code from GitHub and update your local Master version to be identical.

**Never write code while on the master branch or push to the master branch**

 <img src="https://github.com/Rasbandit/Git-Good-Guide/blob/master/Images/Step-2.jpg" />
