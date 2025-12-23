2 
 # GIT BRANCHING
 
This is the documentation that conatins the concepts of Leran Git Branching Learn GIt Branching Git branching allows you to create a separate line of development so you can work on new features or fix bugs without affecting the main code. It helps keep the main branch stable while changes are developed and tested independently. Once the work is complete, the branch can be merged back into the main branch.

Understand what a branch is –a separate line of work from the main code. About Git Commits

A commit in Git is like saving a snapshot of your project at a specific point in time. It records the changes you made to files along with a short message explaining what was changed. Commits help track progress, go back to earlier versions if something goes wrong, and understand who changed what and why in a project.

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


# Introduction to Git Branching

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


# Introduction to Git Merging

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

# Introduction to Rebase

What is Git Rebase
Git rebase is the process of moving or replaying commits from one branch onto another branch, changing the base commit so the history becomes linear.



