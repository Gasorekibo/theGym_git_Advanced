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