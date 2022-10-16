# Git & Github Advanced tutrial

## Interactive Rebase

It is a tool for optimizing and cleaning up your history
it allows you to :

it is meant to update your local history before merging your branch with the team branch that makes it easier to understand the history of the project

- Change commit's message
- Delete a commit
- reorder commits
- combine multiple commits into one
- edit or split an existing commit into multiple new ones

> **Note:** Don't use interactive rebase on a branch that has been pushed to a remote repository

**Steps:**

- determine how far back do you want to go
- use the command

```
`git rebase -i HEAD~<number of commits>`    //-i stands for interactive
```

- you will see a list of commits
- you can change the action of each commit Ex. `pick` to:
  - `edit` : edit the commit
  - `squash` : if you want to combine a commit with the commit above
  - `fixup` : if you want to combine a commit with the commit above and delete the commit message
  - `drop` : if you want to delete a commit
  - `reword` : if you want to update the commit message
  - `exec` : if you want to run a command
  - `break` : if you want to stop the rebase
- save the file and exit
- you will see a list of commits again
- you can change the commit message
- save the file and exit

## Cherry Picking

integrating a commit from one branch to another branch
Situation example of cherry picking: - if you make a commit on the wrong branch and you want to move it to another branch

**Steps:**

- switch to the branch you want to move the commit to
- use the command:
  ```
  git cherry-pick <commit hash>
  ```
- if you want to delete it from the branch you moved it from use the command:
  ```
  git reset --hard HEAD~1
  ```

## Reflog

it is a protocol of head pointer movements
it is used to recover from mistakes

#### Recovering a commit that was deleted

situation example:

- if you reset the head pointer to a commit and you want to go back to the previous commit

**Steps:**

- first you have to find the commit hash of the commit you want to go back to
- use the command:
  ```
  git reflog
  ```
- you will see a list of commits
- find the commit hash of the commit you want to go back to
- then you can get them back in a new branch using the command:
  ```
  git checkout -b <new branch name> <commit hash>
  ```
  or
  ```
  git branch <branch name> <commit hash>
  ```
  or you can also get them back in the same branch using the command:
  ```
  git reset --hard <commit hash>
  ```

#### Recovering a Branch that was deleted

situation example:

- if you deleted a branch and you want to get it back
  **Steps:**
- use the command:
  ```
  git reflog
  ```
- you will see a list of commits and actions you have done
- find the commit or action hash you want to go back to
- then you can get the branch back using the command:
  ```
  git checkout -b <new branch name> <commit hash>
  ```
  or
  ```
  git branch <branch name> <commit hash>
  ```
  - that will create a branch with the same name and data as the deleted branch

## Submodules

it is a way to include another git repository in your project

**Steps:**

- create a new folder in your repo
- go into that new folder and use the command:
  ```
  git submodule add <repo url>     //the repo url is the url of the repo you want to include
  ```
  git regareds adding a submodule as a modification like anyother modification, so you have to commit it

#### what about cloning a repo that has submodules

- when you clone a repo that has submodules, the submodules will not be cloned with it by default

- the repo will be colned normally, but when you try to find the submodules you will only find an empty folders

- to clone the submodules with the repo you have to use the command:

  ```
  git submodule update --init --recursive
  ```

  - this command will clone the submodules

- but if you want to clone the repo and the submodules in one command you can use the command:
  ```
  git clone --recurse-submodules <repo url>
  ```

## Search & Find

searching for a commit or a file in the history of the project

- Filtering your commit history
  - by date --before and --after
    - you can use the command:
      ```
      git log --before="2020-01-01"
      ```
      or
      ```
      git log --after="2020-01-01"
      ```
  - by message --grep
    - you can use the command:
      ```
      git log --grep="commit message or a word in commit message"
      ```
  - by author --author
    - you can use the command:
      ```
      git log --author="author name"
      ```
  - by file -- "file name"
    - you can use the command:
      ```
      git log -- "file name"
      ```
  - by branch "branch name"
    - you can use the command:
      ```
      git log "branch name"
      ```
