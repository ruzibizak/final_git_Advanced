

## Part 2: Branching Basics (10 Challenges)

## Feature Branch Creation:
```bash
git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
 git branch
  ft/branch
* ft/new-feature
  main
  ```

 
  
   ## exercise 2:Working on the Feature Branch
   ```bash
             git add feature.txt
              git commit -m "Implemented core functionality for new feature"
[ft/new-feature 3e72e51] Implemented core functionality for new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt
```
 ## Exercise 3:Switching Back and Making More Changes:
 ```bash
git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS D:\final_git_advanced> git branch
  ft/branch
  ft/new-feature
* main
git add Readme.md
PS D:\final_git_advanced> git commit -m "Updated project readme"
[main 536dafd] Updated project readme
 1 file changed, 16 insertions(+)
 create mode 100644 Readme.md
```
## Exercise 5:Branch Deletion
```bash
        git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was 3e72e51).
```

## exercise 6: Creating a Branch from a Commit
          ```bash
         git checkout -b ft/new-branch-from-commit 3e72e51
Switched to a new branch 'ft/new-branch-from-commit'

user@k25130 MINGW64 /d/final_git_advanced (ft/new-branch-from-commit)
$ git branch
[main 8d5efd2] Updated Readme.md before switching branches
 1 file changed, 28 insertions(+)
 .
```

 ## exercise 7: Branch Merging
 ```bash
git checkout main                                                                             
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)   

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge ft/new-branch-from-commit
Auto-merging Readme.md
CONFLICT (add/add): Merge conflict in Readme.md
Automatic merge failed; fix conflicts and then commit the result.

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git add Readme.md

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git commit -m "Resolved merge conflicts and merged ft/new-branch-from-commit"
[main df114c8] Resolved merge conflicts and merged ft/new-branch-from-commit
```
## Exercise 8:Branch Rebasing
```bash
git fetch origin main
From https://github.com/ruzibizak/final_git_Advanced
 * branch            main       -> FETCH_HEAD

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git rebase main
Current branch main is up to date.
```
## Exercise 9:Renaming Branches
```bash

git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

user@k25130 MINGW64 /d/final_git_advanced (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name
```
## Checking Out Detached HEAD:
```bash

git checkout 188098c
Note: switching to '188098c'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -
If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -
Or undo this operation with:

  git switch -
  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 188098c Implemented test 5

user@k25130 MINGW64 /d/final_git_advanced ((188098c...))
```
## Part 3:Advanced Workflows (10+ Challenges)
## Challenge 1: Stashing Changes
```bash
git stash -u
Saved working directory and index state WIP on main: d6ba385 progress

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git stash list
stash@{0}: WIP on main: d6ba385 progress
```
##  Challenge 2 : Retrieving Stashed Changes:

```bash
git stash pop
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

  (use "git push" to publish your local commits)


nothing to commit, working tree clean
Dropped refs/stash@{0} (da817143d040e165a28ce46ce9c8be861c5789b0)
```
## Challenge 3: Branch Merging Conflicts (Continued)
```bash
git checkout -b feature-branch
Switched to a new branch 'feature-branch'

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ echo "This is a change on the main branch." > example.txt

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git add example.txt
warning: in the working copy of 'example.txt', LF will be replaced by CRLF the next time Git touches it

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git commit -m "Update example.txt on main"
[main a7f47e8] Update example.txt on main
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git checkout feature-branch
Switched to branch 'feature-branch'

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ echo "This is a change on the feature branch." > example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git add example.txt
warning: in the working copy of 'example.txt', LF will be replaced by CRLF the next time Git touches it

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git commit -m "Update example.txt on feature-branch"
[feature-branch c34a382] Update example.txt on feature-branch
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git commit -m "Update example.txt on feature-branch"
[feature-branch c34a382] Update example.txt on feature-branch
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge feature-branch
Auto-merging example.txt
CONFLICT (add/add): Merge conflict in example.txt
Automatic merge failed; fix conflicts and then commit the result.

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git add example.txt

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git commit -m "Resolved merge conflict between main and feature-branch"
[main 3d1baaa] Resolved merge conflict between main and feature-branch

git checkout -b feature-branch
Switched to a new branch 'feature-branch'

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ echo "This is a change on the main branch." > example.txt

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git add example.txt
warning: in the working copy of 'example.txt', LF will be replaced by CRLF the next time Git touches it

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git commit -m "Update example.txt on main"
[main a7f47e8] Update example.txt on main
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git checkout feature-branch
Switched to branch 'feature-branch'

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ echo "This is a change on the feature branch." > example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git add example.txt
warning: in the working copy of 'example.txt', LF will be replaced by CRLF the next time Git touches it

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git commit -m "Update example.txt on feature-branch"
[feature-branch c34a382] Update example.txt on feature-branch
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git commit -m "Update example.txt on feature-branch"
[feature-branch c34a382] Update example.txt on feature-branch
 1 file changed, 1 insertion(+)
 create mode 100644 example.txt

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main

user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
user@k25130 MINGW64 /d/final_git_advanced (feature-branch)
$ git checkout main
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge feature-branch
Auto-merging example.txt
CONFLICT (add/add): Merge conflict in example.txt
Automatic merge failed; fix conflicts and then commit the result.

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git add example.txt

user@k25130 MINGW64 /d/final_git_advanced (main|MERGING)
$ git commit -m "Resolved merge conflict between main and feature-branch"
[main 3d1baaa] Resolved merge conflict between main and feature-branch

```

## challenge 4: Resolving Merge Conflicts with a Merge Tool
```bash
