# Git Tips

Use this handy git comments and guide to enhance your workflow. :)

Inspired by: https://www.atlassian.com/git , https://learngitbranching.js.org/

### Getting & Creating Projects

| Command                                                           | Description                                |
| ----------------------------------------------------------------- | ------------------------------------------ |
| `git init`                                                        | Initialize a local Git repository          |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Clone to existing directory

Form your existing directory

| Command                                                        | Description                                 |
| -------------------------------------------------------------- | ------------------------------------------- |
| `git init`                                                     | Initialize a local Git repository           |
| `git remote add origin [https|ssh:path/to/the/repository.git]` | Add the remote from where you want to clone |
| `git pull origin master`                                       | Pull and merge with local git               |

### Basic Snapshotting

| Command                            | Description                                       |
| ---------------------------------- | ------------------------------------------------- |
| `git status`                       | Check status                                      |
| `git add [file-name.txt]`          | Add a file to the staging area                    |
| `git add -A`                       | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes                                    |
| `git rm -r [file-name.txt]`        | Remove a file (or folder)                         |

### Branching & Merging

| Command                                              | Description                                             |
| ---------------------------------------------------- | ------------------------------------------------------- |
| `git branch`                                         | List branches (the asterisk denotes the current branch) |
| `git branch -a`                                      | List all branches (local and remote)                    |
| `git branch [branch name]`                           | Create a new branch                                     |
| `git branch -d [branch name]`                        | Delete a branch                                         |
| `git push origin --delete [branch name]`             | Delete a remote branch                                  |
| `git checkout -b [branch name]`                      | Create a new branch and switch to it                    |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it                  |
| `git checkout [branch name]`                         | Switch to a branch                                      |
| `git checkout -`                                     | Switch to the branch last checked out                   |
| `git checkout -- [file-name.txt]`                    | Discard changes to a file                               |
| `git merge [branch name]`                            | Merge a branch into the active branch                   |
| `git merge [source branch] [target branch]`          | Merge a branch into a target branch                     |
| `git stash`                                          | Stash changes in a dirty working directory              |
| `git stash clear`                                    | Remove all stashed entries                              |

## Rename a Git Branch – Local

Rename a Git branch with the -m command option

`git branch -m new-name`

Rename a Git branch from another branch

`git branch -m old-name new-name`

### Sharing & Updating Projects

| Command                                                                           | Description                                                 |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `git push origin [branch name]`                                                   | Push a branch to your remote repository                     |
| `git push -u origin [branch name]`                                                | Push changes to remote repository (and remember the branch) |
| `git push`                                                                        | Push changes to remote repository (remembered branch)       |
| `git push origin --delete [branch name]`                                          | Delete a remote branch                                      |
| `git pull`                                                                        | Update local repository to the newest commit                |
| `git pull origin [branch name]`                                                   | Pull changes from remote repository                         |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git`     | Add a remote repository                                     |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH                     |

### Inspection & Comparison

| Command                                    | Description                    |
| ------------------------------------------ | ------------------------------ |
| `git log`                                  | View changes                   |
| `git log --summary`                        | View changes (detailed)        |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Git Hard Reset Recover

Inspired form : https://medium.com/@CarrieGuss/how-to-recover-from-a-git-hard-reset-b830b5e3f60c

## Can I recover Git Files?

Yes, you can, As far I know git never delete any files form your system.

#### Scenario

I did a hard reset after adding files to be committed but BEFORE committing them. Git deleted all the files on my actual working directory.
(Or, Git replaced all my new fancy clean files with old ugly bad files.)

> invisible path: .git/lost-found/other

`git fsck`

`git fsck --lost-found`

`git cat-file -p $blob > $blob.txt`
