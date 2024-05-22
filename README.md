# Git Advanced Exercises
## Question 1

```bash 
echo "# theGym_git_Advanced" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Gasorekibo/theGym_git_Advanced.git
git push -u origin main
$ touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main 3abf696] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main f6eec5c] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main 324ad16] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log
commit 324ad16d26fd6a20b2ea0f7be19a222b66e6d064 (HEAD -> main)
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:11 2024 +0200

    chore: Create third and fourth files

commit f6eec5c6ef42c401a38dcaa0c765fbb6349eb183
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:10 2024 +0200

    chore: Create another file

commit 3abf69638f26d39a0a0408d233e06c077247429a
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:10 2024 +0200

    chore: Create initial file

commit b801c44c31b9400d789e3f1dffc0f042b67c7f27 (origin/main)
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:13:03 2024 +0200

    first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git commit --amend -m "added the test4.md file"
[main 94049e7] added the test4.md file
 Date: Mon May 20 18:21:11 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git add test4.md 

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test4.md


Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git commit --amend -m "added the test4.md file"
[main a95b98a] added the test4.md file
 Date: Mon May 20 18:21:11 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$
```

### Exercise 2
```bash
git rebase -i 3abf696
Stopped at f6eec5c...  chore: Create another file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 1/3)
$ git commit --amend
[detached HEAD 27093a2] create second file
 Date: Mon May 20 18:21:10 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 1/3)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log --oneline
2c8a3c6 (HEAD -> main) added the test4.md file
a8b3e28 create Third and fourth files
27093a2 create second file
3abf696 chore: Create initial file
b801c44 first commit
```

### Question 3
```bash
pick 3abf696 chore: Create initial file
# This is a combination of 2 commits.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git rebase -i HEAD~5
[detached HEAD 62f9c42] chore: Create initial file
 Date: Mon May 20 18:21:10 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log --oneline
c734dd3 (HEAD -> main) update readme file
5368c87 added the test4.md file
d6de68a create Third and fourth files
62f9c42 chore: Create initial file
b801c44 first commit
```

### Question 4
```bash
 git rebase -i --root
Stopped at d6de68a...  create Third and fourth files
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git reset HEAD~

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git status
interactive rebase in progress; onto 32db6df
Last commands done (3 commands done):
   pick 62f9c42 chore: Create initial file
   edit d6de68a create Third and fourth files
  (see more in file .git/rebase-merge/done)
Next commands to do (3 remaining commands):
   pick 5368c87 added the test4.md file
   pick c734dd3 update readme file
  (use "git rebase --edit-todo" to view and edit)
You are currently editing a commit while rebasing branch 'main' on '32db6df'.
  (use "git commit --amend" to amend the current commit)
  (use "git rebase --continue" once you are satisfied with your changes)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git add test3.md 

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git commit -m "create third file"
[detached HEAD b6ac2af] create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git add test4.md 

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git commit -m "create fourth file"
[detached HEAD 9d9ab0a] create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 3/6)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log --oneline
8e191bc (HEAD -> main) update README file
d0475e5 update readme file
b0df05f added the test4.md file
9d9ab0a create fourth file
b6ac2af create third file
62f9c42 chore: Create initial file
b801c44 first commit
```

### Question 4
```bash
git log --oneline
021cdb9 (HEAD -> main) update readme file
b0df05f added the test4.md file
9d9ab0a create fourth file
b6ac2af create third file
62f9c42 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git rebase -i 62f9c42
[detached HEAD 729a140] create third and fourth files create third file
 Date: Tue May 21 12:43:58 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

### Question 5

``` bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log --oneline
021cdb9 (HEAD -> main) update readme file
b0df05f added the test4.md file
9d9ab0a create fourth file
b6ac2af create third file
62f9c42 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git rebase -i 62f9c42
[detached HEAD 729a140] create third and fourth files create third file
 Date: Tue May 21 12:43:58 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

### Question 6
```bash
$ git log --oneline
378e64c (HEAD -> main) updated README file
1856bc7 unwanted commit
e023931 update readme file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log --oneline
112ecf4 (HEAD -> main) updated README file
e023931 update readme file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
b801c44 first commit
```

### Exercise 7
```bash
git log
commit 481198944ad3aab952228e0931b75286213f7c58 (HEAD -> main)
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Tue May 21 14:12:27 2024 +0200
pick 6de25ec added the test4.md file

    updated README file

commit e023931163eb54890b851f83e4710dcdde889c9f
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Tue May 21 12:34:13 2024 +0200

    update readme file

    update README file

    Update README file

commit 6de25ece9d330db7912dd163fcb18cf8cab8ce0e
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:11 2024 +0200

    added the test4.md file


Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git rebase -i HEAD~3
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
error: could not apply 4811989... updated README file
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 4811989... updated README file

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main|REBASE 2/3)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git log
commit 6a62618f678dec5c063aa18e8b13bd176b7aa8d2 (HEAD -> main)
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Tue May 21 14:12:27 2024 +0200

    updated README file

commit 6de25ece9d330db7912dd163fcb18cf8cab8ce0e
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:11 2024 +0200

    added the test4.md file

commit 729a140271b6232904c4c4399078cb6b9c6e41e4
```
### Question 8

```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ touch test5.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git add test5.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)
$ git commit -m "implement test 5"
[ft/branch d923edd] implement test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)
$ git log --oneline
d923edd (HEAD -> ft/branch) implement test 5
bd5572d (origin/main, main) solve conflict
ef8165f updated README file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
cc08534 Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
3033012 added the test4.md file
3cf99b4 create Third and fourth files
bc269c4 added the test4.md file
f6eec5c chore: Create another file
3abf696 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git cherry-pick --no-commit f6eec5c 

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git diff

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git diff f6eec5c
diff --git a/README.md b/README.md
index 84a0d28..8f11b92 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,346 @@
-# theGym_git_Advanced
+# Git Advanced Exercises
+## Question 1
+
+```bash 
+echo "# theGym_git_Advanced" >> README.md
+git init
+git add README.md
+git commit -m "first commit"
+git branch -M main
+git remote add origin https://github.com/Gasorekibo/theGym_git_Advanced.git
+git push -u origin main
+$ touch test{1..4}.md
+git add test1.md && git commit -m "chore: Create initial file"
+git add test2.md && git commit -m "chore: Create another file"
+git add test3.md && git commit -m "chore: Create third and fourth files"
+[main 3abf696] chore: Create initial file
+ 1 file changed, 0 insertions(+), 0 deletions(-)
+ create mode 100644 test1.md
+[main f6eec5c] chore: Create another file
+ 1 file changed, 0 insertions(+), 0 deletions(-)
+ create mode 100644 test2.md
+[main 324ad16] chore: Create third and fourth files
+ 1 file changed, 0 insertions(+), 0 deletions(-)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git show commit f6eec5c
fatal: ambiguous argument 'commit': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/branch)        
$ git show f6eec5c
commit f6eec5c6ef42c401a38dcaa0c765fbb6349eb183
Author: Gasorekibo <m.gasore@alustudent.com>
Date:   Mon May 20 18:21:10 2024 +0200

    chore: Create another file

diff --git a/test2.md b/test2.md
new file mode 100644
index 0000000..e69de29
```

### Question 9

```bash
git log --graph
* commit d923edd545b89378edc29ec00f45b8bebe71f1b7 (HEAD -> ft/branch)
| Author: Gasorekibo <m.gasore@alustudent.com>
| Date:   Tue May 21 14:42:44 2024 +0200
| 
|     implement test 5
|   
*   commit bd5572d2663f8f39a6a30b1815155165d83cf63d (origin/main, main)
|\  Merge: ef8165f cc08534
| | Author: Gasorekibo <m.gasore@alustudent.com>
| | Date:   Tue May 21 14:40:01 2024 +0200
| | 
| |     solve conflict
| |   
| *   commit cc08534f65fc17508b096fa7fcba3ce2ac22ad21
| |\  Merge: 3033012 bc269c4
| | | Author: Gasorekibo <m.gasore@alustudent.com>
| | | Date:   Tue May 21 12:27:07 2024 +0200
| | | 
| | |     Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
| | |
| | * commit bc269c4e6623a6d946f38a98a07c89725196c039
```

# Git Advanced Exercises Part 2

## Question 1
```bash
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git branch
  ft/branch
* ft/new-feature
  main
```

## Question 2
```bash
$ touch feature.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git add feature.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git commit -m "implemented core functionfunctionality for new feature"
[ft/new-feature 857d061] implemented core functionfunctionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```

## Question 3
```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git checkout main
Switched to branch 'main'
M       README.md
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git branch
  ft/branch
  ft/new-feature
* main
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ touch readme.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git add readme.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git commit -m "update project readme"
[main 209c04f] update project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
 ```

 ## Question 5

 ```bash
 git checkout ft/new-feature
Switched to branch 'ft/new-feature'
M       README.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git merge main
Merge made by the 'ort' strategy.
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-feature)
$ git checkout main
Switched to branch 'main'
M       README.md
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was e940c07).
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git branch
  ft/branch
* main
```
## Question 6
```bash
 git checkout -b ft/new-branch-from-commit 279701b
Switched to a new branch 'ft/new-branch-from-commit'
M       README.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git branch
  ft/branch
* ft/new-branch-from-commit
  main
```

## Question 7
```bash
git merge main
Updating 279701b..209c04f
Fast-forward
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git status
On branch ft/new-branch-from-commit
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Question 8
```bash
git log --oneline
dea32cd (HEAD -> ft/new-branch-from-commit) update project readme
279701b (origin/main) done with git advanced part1
bd5572d solve conflict
ef8165f updated README file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
cc08534 Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
3033012 added the test4.md file
3cf99b4 create Third and fourth files
bc269c4 added the test4.md file
f6eec5c chore: Create another file
3abf696 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git log --oneline
8270f81 (HEAD -> ft/new-branch-from-commit) update project readme
209c04f (main) update project readme
279701b (origin/main) done with git advanced part1
bd5572d solve conflict
ef8165f updated README file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
cc08534 Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
3033012 added the test4.md file
3cf99b4 create Third and fourth files
bc269c4 added the test4.md file
f6eec5c chore: Create another file
3abf696 chore: Create initial file
b801c44 first commit
```
## Question 9
```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git branch
  ft/branch
* ft/new-branch-from-commit
  main

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/improved-branch-name)
$ git branch
  ft/branch
* ft/improved-branch-name
  main
```

## Question 10

```bash
git log --oneline
d13d019 (HEAD -> ft/improved-branch-name) update project readme
209c04f (main) update project readme
279701b (origin/main) done with git advanced part1
bd5572d solve conflict
ef8165f updated README file
6de25ec added the test4.md file
729a140 create third and fourth files create third file
62f9c42 chore: Create initial file
cc08534 Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
3033012 added the test4.md file
3cf99b4 create Third and fourth files
bc269c4 added the test4.md file
f6eec5c chore: Create another file
3abf696 chore: Create initial file
b801c44 first commit

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/improved-branch-name)
$ git checkout cc08534
Note: switching to 'cc08534'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at cc08534 Merge branch 'main' of https://github.com/Gasorekibo/theGym_git_Advanced
```

# Git Advanced Exercises Part 3

## Question 1
```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git stash
Saved working directory and index state WIP on main: 06d19c3 update project readme

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

## Question 2
```bash
git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git stash pop
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")    
Dropped refs/stash@{0} (e63f7e2ededad15f0645b4a24397952843a6a045)    

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Question 3 Conflict
```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git checkout ft/improved-branch-name 
Switched to branch 'ft/improved-branch-name'
M       README.md
Your branch is up to date with 'origin/ft/improved-branch-name'.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/improved-branch-name)
$ git add test4.md 

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/improved-branch-name)
$ git commit -m 'modified to cause conflict'
[ft/improved-branch-name 87e573b] modified to cause conflict
 1 file changed, 1 insertion(+)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (ft/improved-branch-name)
$ git checkout main
Switched to branch 'main'
M       README.md
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git merge ft/improved-branch-name
Auto-merging test4.md
CONFLICT (content): Merge conflict in test4.md
Automatic merge failed; fix conflicts and then commit the result.

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git$ git merge ft/improved-branch-name 
Already up to date.
```

## Question 6 .gitignore
```bash
$ ls
README.md  readme.txt  test1.md  test2.md  test3.md  test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)  $ ls
README.md  readme.txt  test1.md  test2.md  test3.md  test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)


$ touch .gitignore

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ ls
README.md  readme.txt  test1.md  test2.md  test3.md  test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ ls -al
total 42
drwxr-xr-x 1 Lenovo 197121     0 May 22 17:17 ./
drwxr-xr-x 1 Lenovo 197121     0 May 20 18:08 ../
drwxr-xr-x 1 Lenovo 197121     0 May 22 17:09 .git/
-rw-r--r-- 1 Lenovo 197121     0 May 22 17:17 .gitignore
-rw-r--r-- 1 Lenovo 197121 26327 May 22 17:09 README.md
-rw-r--r-- 1 Lenovo 197121    33 May 22 16:28 readme.txt
-rw-r--r-- 1 Lenovo 197121     0 May 21 12:42 test1.md
-rw-r--r-- 1 Lenovo 197121     0 May 21 12:42 test2.md
-rw-r--r-- 1 Lenovo 197121     0 May 21 12:57 test3.md
-rw-r--r-- 1 Lenovo 197121    42 May 22 17:08 test4.md

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ cat .gitignore
/temp
```
## Question 7
```bash
git branch
  ft/branch
  ft/improved-branch-name
* main

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag v1.0

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag
v1.0
```
## Question 8 Listing tag and delete
```bash
Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag v1.1

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag
v1.0
v1.1

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag -d v1.1
Deleted tag 'v1.1' (was 7f881af)

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git tag
v1.0
```

## Question 9 Pushing local to remote repo

```bash
 git status
On branch main
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

no changes added to commit (use "git add" and/or "git commit -a")

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git add .

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git commit -m "pushing to remote repo"
[main 5105a15] pushing to remote repo
 2 files changed, 176 insertions(+)
 create mode 100644 .gitignore

Lenovo@Mugwaneza-Gasore MINGW64 ~/OneDrive/Desktop/The Gym/git-advanced (main)
$ git push
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (11/11), 1.79 KiB | 914.00 KiB/s, done.
Total 11 (delta 6), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (6/6), completed with 2 local objects.
To https://github.com/Gasorekibo/theGym_git_Advanced.git
   279701b..5105a15  main -> main
```