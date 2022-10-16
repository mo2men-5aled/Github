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
