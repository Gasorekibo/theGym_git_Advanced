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