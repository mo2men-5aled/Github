# Git & Github

## 1- Git & Github introduction

### What is Git..?

Git is a Version control software that allows save each time you make a change so if you make a mistake or you want to update some thing you can look back and update that or undo the change you have done

### What is GitHub..?

Github is a collaboration website that interacts with git

## 2- Github Hub Workflow

When start working on a project, this project stored in a repository,all the code found in a branch called master we don't want to make changes direct to the master branch

- **Branching :**
  creating branch from the master is like making an exact replica of the master branch, so you have a safe sandbox to make changes without affecting the master

- **Commits :**
  making a commit is like saving the changes you have made by taking a snapshot at that point of time

- **Pull request :**
  comparing the branch you made with another branch it gives you an oportunity to look at the differences between those two branches and show other people those differences

- **Collaborate :**
  giving a feedback on that pull request (you to others or others to you)

- **Merge :**
  once you are in a good place then you merge, when you merging you take the branch and commits you made and put them back to the master

## 3- Github Hub Workflow for Open Source

if you are working on a project that you don't have a collaborator access to

- **Fork :**
  create an exact copy of another repositpry but under your account so you have a right access

## 4- Github Hub Cloning and working locally

- Working Locally is to work in your on text editor on your computer without network access
- **Cloning :**
  taking a copy from the remote branch to work on it locally

## 5- Git Commands

- git clone : used for cloning a repository

```
git clone <url>
```

- git pull : used for pulling the latest changes from the remote repository

```
git pull <remote> <branch>
```

- git branch : used for creating a new branch

```
git branch <branch name>
```

- git checkout : used for switching between branches or moving to a specific commit

```
git checkout <branch name>
```

- git status : used for checking the status of the repository (what files are changed)

```
git status
```

- git add : used for adding files to the staging area

```
git add <file name>  // add a specific file
git add .  // add all files
```

- git commit : used for committing the changes to the local repository

```
git commit -m "commit message" // commit with a message
git commit -am "commit message" // add and commit with a message
```

the option -am is used to add and commit at the same time but only the existing files not the new files you have to add them first

- git push : used for pushing the changes to the remote repository

```
git push <remote> <branch>
```

## 6- How commit works

- commit is represented by 40 characters SHA-1 hash
- it includes :

  - **blobs:** files and changes made to them

  - **metadata:** author that made the commit , date that commit made at , message that commit has

## 7- 2-step commit

- git add : add the changes or files you have changed to the staging area
- git commit : save the changes that found in the staging area to the history of the repository with the 40 characters SHA-1 hash

## 8- Merging

add the changes from one branch to the master branch or another branch

- **Remote :** merge on github
- **Local :** merge on your computer on the remote using "git merge" command

```
git merge <branch name> // merge that branch to the current branch
```

- before merging you have to make sure that you are on the branch you want to merge to

- befor merging you can use "git diff" command to see the differences between the branches

```
git diff <branch name>       // compare the current branch with the branch you want to merge
```

## 9- Merge Conflicts

merge cnflicts happens when you have two branches that have changes on the same line of code or in the same file

- run "git status" to see the files that have conflicts

## 10- Rebasing

when using git rebase you are changing the base or history of your branch, you are taking the commits that you have made and replaying them on top of the branch you are rebasing on

```
git rebase <branch name> // rebase the current branch on top of the branch specified in the command
```

## 10- Undo Commit

how do i undo a commit:

- **git revert :** used for undoing a commit and creating a new commit

```
git revert       // revert the last commit
git revert <commit hash>       // revert the commit with the commit hash
```

- **git reset :** used for undoing a commit and moving the HEAD pointer to a specific commit

```
git reset       // reset the HEAD pointer to the last commit
git reset <commit hash>       // reset the HEAD pointer to the commit hash
```

- **git commit--amend :** used for undoing a commit and adding the changes to the previous commit

```
git commit --amend       // undo the last commit and add the changes to the previous commit
```

- **git cherry-pick :** used for undoing a commit and moving the changes to a new branch

```
git cherry-pick       // move the changes to a new branch
git cherry-pick <commit hash>       // move the commit with the commit hash to a new branch
```
