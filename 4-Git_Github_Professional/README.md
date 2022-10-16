# Git & Github Professional

## 1- The Perfect Commit

the bigger the commit contains main topics and changes, the harder it is to understand it.

**rules :**

1- only combine changes from the same topic in one commit
if you made more than one change in one file, but those changes are not related to the same topic so you need to split them into multiple commits by using those commands:

```
git add -p   //-p stands for patch
```

then it will show you the hunks of the file and you can choose which hunk you want to add to the staging area

2- the message

- the subject should be a brief summary of the changes
- the body should be a detailed explanation of the changes

## 2- Branching Strategies

- use branches to isolate your work from the master branch
- use branches to work on multiple features at the same time
- use branches to work on a feature without affecting the master branch

**GitFlow :**

more structured branching strategy, more rules to follow

- long running branches : master or main and develop
- short living branches : feature, release, hotfix

1- master branch : the main branch that contains the production code
2- feature branch : a branch that contains the changes for a specific feature
3- release branch : a branch that contains the changes that are ready to be released
4- hotfix branch : a branch that contains the changes that are urgent and need to be released immediately

**GitHub Flow :**
long running branches : master or main and develop

- it exists through the lifetime of the project
- no direct commits to the master branch

short living branches : feature branch

- it is for a specific feature or bugs that need to be fixed or refactoring the code or experiments
- it is created from the master branch or the develop branch
- it will be deleted after merge or rebase it to the master branch or develop branch

- use the feature branch for all the changes you are going to make

> what is the best branching strategy?

- there is no best branching strategy it depends on understanding the project, the team and the release cycle

## 3- Pull Request

- it is a way to collaborate with other people on github, you are inviting them to review your code and give you feedback before merging it to the master branch

- on forking : a fork is your personal copy of someone else's project, you can make changes to it without affecting the original project and you can send a pull request to the original project to merge your changes

**notes :** pull request based on branches not on commits

## 4- Merge Conflicts

- it happens when :

  - merging
  - rebasing
  - cherry-picking
  - pulling
  - stashing

- how to undo a merge conflict :

```
  git reset --abort
  git rebase --abort
```

- how to solve a merge conflict :

  by cleaning up the file :^)

  - you talk to the other teammate who made the other changes and decide which changes to keep but it is not always possible to do that
    so you need to make a decision by yourself and you can do that by looking at the changes and decide which one to keep and which one to delete and then you need to commit the changes and push it to the remote branch again also you can use this command to open the conflicted file in your editor :

  ```
    git mergetool
  ```
