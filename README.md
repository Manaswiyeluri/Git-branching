
 # GIT BRANCHING
 
This is the documentation that conatins the concepts of Leran Git Branching.

# Level-1 [Introduction Sequence]

# 1.Introduction to Git Commits

### **What is Git Commit?**
A Git commit is a record that saves the current state of a project in a Git repository. It stores the changes made to files along with a message describing those changes, allowing Git to track the project’s history over time.

![1000161779](https://github.com/user-attachments/assets/7294330f-1b9d-487c-835d-75dfe7706e1c)

Commands Executed

```
git commit
```

```
git commit
```

This screenshots shows hoe commits are created in git

C0, C1, C2, C3 are commits

Each circle represents one commit

The arrows show the order of commits

C0 → first commit

C3 → latest commit

main* shows that you are currently on the main branch, and it points to the latest commit (C3)


# 2.Introduction to Git Branching

### **What is Git Branch?**

A branch in Git is like a separate workspace for your code. It allows you to work on new features or fixes without affecting the main code

### **What is Git Chechout?**

The git checkout command is used to switch between these branches, so your files and code update to match the branch you select.


# Commands Executed
```bash
git branch bugfix
```

```
git checkout bugfix
```

This screenshot shows how to create and switch to a new branch in Git using Learn Git Branching.

The commits C0 and C1 are displayed, with C1 being the latest commit.

A new branch named bugfix has been created from commit C1 using git branch bugfix, and it has been checked out using git checkout bugfix.

The * symbol next to bugfix indicates that HEAD is currently on this branch.

The main branch still points to commit C1, but the active branch is now bugfix.
![1000161781](https://github.com/user-attachments/assets/67ecde72-76d5-4108-ae0b-ef8e78a6b0fb)


# 3.Introduction to Git Merging

Git merging is the process of combining changes from one branch into another branch. It is usually used after completing work on a feature or bug-fix branch, to bring those changes back into the main branch. Merging helps keep all work together in one final version of the project without losing any changes.
![1000161784](https://github.com/user-attachments/assets/e1949c69-6dc2-4aaa-bdef-6115091c9cb5)

commands executed

```
git branch bugFix
```
```
git checkout bugFix
```
```
git commit
```
```
git checkout main
```
```
git commit
```
```
git merge bugFix
```

About (Git Merging – simple explanation)

This screenshot shows Git merging using the Learn Git Branching tool. First, a new branch called bugFix is created from the main branch, and a commit is made on the bugFix branch to fix an issue.

Then, the user switches back to the main branch and makes another commit there.

Finally, the command git merge bugFix is used to merge the changes from the bugFix branch into the main branch. After merging, the main branch contains all commits from both branches, showing how Git combines work done in different branches into one complete history.

# 4.Introduction to Rebase

What is Git Rebase
Git rebase is the process of moving or replaying commits from one branch onto another branch, changing the base commit so the history becomes linear.

![1000161788](https://github.com/user-attachments/assets/01ee381f-4368-419e-a17b-9965adaf743b)
# Commands Executed
```bash
git branch bugfix
```
```
git checkout bugfix
```
```
git commit
```
```
git checkout main
```
```
git commit
```
```
git checkout bugfix
```
```
git rebase main
```

This screenshot shows how rebasing works in Git using two branches.

The circles (C0, C1, C2, C3) represent commits created at different times on different branches.

The main branch has its own commits, and the bugFix* label shows the branch where the bug fix work is done.

First, commits are made separately on the main and bugFix branches.

When the command git rebase main is used on the bugFix branch, Git takes the bug fix commit and places it on top of the latest commit of the main branch.

After rebasing, both branches contain the same changes, and the commit history becomes clean and straight.

This helps us understand how Git can organize commits neatly while keeping all changes.

The commit history begins linearly from C0 to C1, after which it splits into two branches. 

The main branch points to commit C3, while the bugfix* branch is currently checked out and points to C2, as indicated by the * symbol showing that HEAD is on the bugfix branch. 

The diagram shows that the bugfix commit has been moved and reapplied on top of the latest commit of the main branch, resulting in a straight, linear history. 

The renaming of the commit to C2′ visually represents that the commit was recreated during the rebase process.


# Level-2 [Ramping Up]
# 1.Detach yo' HEAD
Detach yo’ HEAD means that you are no longer working on a branch.

Normally, HEAD points to a branch like main or bugFix. In a detached HEAD state, HEAD points directly to a commit instead of a branch.

This usually happens when you checkout a specific commit.

In this state, you can look at old code or test something, but any new commit you make will not belong to a branch.

If you switch to another branch, those commits can be lost unless you create a new branch.

This helps us understand why staying on a branch is important when making changes.

![1000161810](https://github.com/user-attachments/assets/856dca42-8826-490a-893c-5dd8e4d0daf5)

# Command Executed

```
git checkout C4
```

This screenshot shows what happens when HEAD is detached in Git.

The commits (C0, C1, C2, C3, C4) show the history of the project.

At first, HEAD is normally connected to a branch like main or bugFix.

When the command git checkout C4 is used, Git moves HEAD directly to commit C4.

Now, HEAD is not pointing to any branch, it is pointing only to that commit.

The branches (main and bugFix) stay where they were and do not move.

This state is called detached HEAD.

It helps us understand how Git can look at any old commit without changing branch history.

# 2.Relative Refs (^)
Remembering full commit hashes in Git is hard and annoying because they are very long.

In real projects, you don’t see a picture of commits, so you use git log to find commit hashes.

The good thing is, Git does not need the full hash. You can type only the first few characters, as long as they are unique.

Still, using hashes is not very convenient. That’s why Git provides relative references.

Relative references let you move around commits starting from something easy to remember, like HEAD or a branch name.

There are two simple relative references:

^ → moves one commit back

~ → moves multiple commits back

This makes it much easier to move through commit history without typing long hashes.

![1000161814](https://github.com/user-attachments/assets/7b325521-910e-465c-950f-0497137f8b1f)

# Commands Executed
```
git checkout bugFix
```
```
git checkout C3
```

In these screenshot
Git checkout bugFix moves you to the bugFix branch.

Git checkout C3 moves HEAD to commit C3, not to a branch, so this is called detached HEAD.

The ^ symbol means go to the previous commit.

3.Relative Refs #2 (~)
The tilde (~) operator is used to move back multiple commits at once.

Instead of using ^ again and again, ~ makes it easier and faster.

The number after ~ tells Git how many commits to go back.
# ![1000161812](https://github.com/user-attachments/assets/d2a47cda-1aee-429d-901d-dbd3a3a321b5)

# Commands Executed
```
git checkout C1
```
```
git branch -f bugFix C0
```
```
git branch -f main C6
```
These screenshot shows Git checkout C1 moves you directly to commit C1.

Git branch -f bugFix C0 forces the bugFix branch to point to commit C0.

Git branch -f main C6 forces the main branch to point to commit C6.

# 4.Reversing Changes in Git
When you mess up in Git, you have two main ways to fix it:

1.git reset – “Go back in time.”

It’s like saying, “Forget I ever made this change.”

Can remove your files or commits completely.

Be careful, because once it’s gone, it might be hard to get back.

2.git revert – “Make a new fix.”

It’s like saying, “I made a mistake, so here’s a new commit that undoes it.”

Your history stays safe.
![1000161829](https://github.com/user-attachments/assets/dcd50119-a398-4c72-ab0d-dddee4b03979)

# Commands Executed
```
git checkout local
```
```
git reset --hard C1
```
```
git checkout pushed
```
```
git revert pushed
```
Git checkout local moves you to the local branch.

Git reset --hard C1 moves the branch back to commit C1 and removes later changes.

Git checkout pushed switches you to the pushed branch.

Git revert pushed creates a new commit that undoes the changes made in the pushed commit.

# Level-3 [Moving Work Around]
# 1.Cherry-pick Intro
Git cherry-pick means taking one specific commit from another branch and applying it to your current branch.
![1000161827](https://github.com/user-attachments/assets/0e3860f5-339c-4b06-b0ff-8e17edc54a7b)
# Command Executed
```
git cherry-pick C3 C4 C7
```
C3- Git copies the changes from commit C3 and adds them to main as a new commit.

C4- Then Git copies the changes from commit C4 and adds them after C3 on main.

C7- Finally, Git copies the changes from commit C7 and adds them after C4 on main.

# 2.Interactive Rebase Intro
It lets you fix and arrange your past commits in a clean and simple way before saving them.
![1000161823](https://github.com/user-attachments/assets/b2bd7107-f13e-4f6b-93fb-532bbc07b528)

# Command Executed
```
git rebase -i HEAD~4
```
HEAD~4 → go back 4 commits from where you are now

rebase -i → open an interactive screen to edit those commits

