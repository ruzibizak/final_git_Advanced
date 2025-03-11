

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

 
  
   ## exercise 2:Working on the Feature Branches
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
```
## Challenge 5: Understanding Detached HEAD State
```bash 
git add .

user@k25130 MINGW64 /d/final_git_advanced (Detached_Head)
$ git commit -m "Your Detarched changes"
[Detached_Head 9d8db37] Your Detarched changes
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Detached.txt

user@k25130 MINGW64 /d/final_git_advanced (Detached_Head)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge Detached_Head
Updating 869c232..9d8db37
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge Detached_Head
Updating 869c232..9d8db37

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git merge Detached_Head
Updating 869c232..9d8db37
Updating 869c232..9d8db37
Fast-forward
 Detached.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Detached.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Detached.txt

```
## challenge 6: Ignoring Files/Directories
```bash
 git add .gitignore

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git commit -m "Add .gitignore file to exclude unnecessary files"
[main ce60855] Add .gitignore file to exclude unnecessary files
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
 git status --ignored
On branch main
Your branch is ahead of 'origin/main' by 8 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   .gitignore
        modified:   Readme.md

Ignored files:
  (use "git add -f <file>..." to include in what will be committed)
        example.txt
   ```
## challenge 7: Working with Tags
```bash
git tag v1.0

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git tag
v1.0

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git push origin v1.0
Enumerating objects: 31, done.
Counting objects: 100% (31/31), done.
Delta compression using up to 4 threads
Compressing objects: 100% (24/24), done.
Writing objects: 100% (27/27), 3.09 KiB | 351.00 KiB/s, done.
Total 27 (delta 10), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (10/10), done.
To https://github.com/ruzibizak/final_git_Advanced.git
 * [new tag]         v1.0 -> v1.0

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git show v1.0
commit 7dd9b84d9a66a65aa4605880aafa862b6912d8d2 (HEAD -> main, tag: v1.0)
Author: Your Name <you@example.com>
Date:   Tue Mar 11 11:13:09 2025 +0200

    Ignored example.txt

diff --git a/example.txt b/example.txt
deleted file mode 100644
index 66936ce..0000000
--- a/example.txt
+++ /dev/null
@@ -1,2 +0,0 @@
-Change from feature branch
-Change from main branch

user@k25130 MINGW64 /d/final_git_advanced (main)
```
## Challenge 8:Listing and Deleting Tags
```bash
git tag
v1.0

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 7dd9b84)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git push origin --delete v1.0
To https://github.com/ruzibizak/final_git_Advanced.git
 - [deleted]         v1.0

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git tag

user@k25130 MINGW64 /d/final_git_advanced (main)
```

## Challenge 9: Pushing Local Work to Remote Repositories

```bash
git add .

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git commit -m "progress"
[main c6501df] progress
 2 files changed, 126 insertions(+), 1 deletion(-)

user@k25130 MINGW64 /d/final_git_advanced (main)
$ git push origin main 
Enumerating objects: 37, done.
Counting objects: 100% (37/37), done.
Delta compression using up to 4 threads
Compressing objects: 100% (27/27), done.
Writing objects: 100% (31/31), 4.39 KiB | 224.00 KiB/s, done.
Total 31 (delta 12), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (12/12), completed with 1 local object.
To https://github.com/ruzibizak/final_git_Advanced.git
   f470844..c6501df  main -> main

user@k25130 MINGW64 /d/final_git_advanced (main)
```
