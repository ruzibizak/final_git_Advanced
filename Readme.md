

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



