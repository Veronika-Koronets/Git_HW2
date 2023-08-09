# Git_HW2

## 1. In local repository make branches for:
-  Postman
- Jmeter
- CheckLists
- Bag Reports
- SQL
- Charles
- Mobile testing
```
kv@kvPC MINGW64 /d
$ git clone https://github.com/Veronika-Koronets/Git_HW2.git

Cloning into 'Git_HW2'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

kv@kvPC MINGW64 /d
$ cd Git_HW2

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch Postman

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch Jmeter

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch CheckLists

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch Bug_Reports

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch SQL

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch Charles

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch Mobile_testing

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git branch
  Bug_Reports
  Charles
  CheckLists
  Jmeter
  Mobile_testing
  Postman
  SQL
* main

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

## 2. Push all the branches to the remote repository

```
kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git push origin -all
error: did you mean `--all` (with two dashes)?

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git push origin --all
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Veronika-Koronets/Git_HW2.git
 * [new branch]      Bug_Reports -> Bug_Reports
 * [new branch]      Charles -> Charles
 * [new branch]      CheckLists -> CheckLists
 * [new branch]      Jmeter -> Jmeter
 * [new branch]      Mobile_testing -> Mobile_testing
 * [new branch]      Postman -> Postman
 * [new branch]      SQL -> SQL
```

## 3. In Bug_Reports branch, create a text document with the structure of the bug report
```
kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git checkout Bug_Reports
Switched to branch 'Bug_Reports'

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git branch
* Bug_Reports
  Charles
  CheckLists
  Jmeter
  Mobile_testing
  Postman
  SQL
  main

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ ls -la
total 13
drwxr-xr-x 1 kv 197121 0 Aug  9 21:52 ./
drwxr-xr-x 1 kv 197121 0 Aug  9 21:30 ../
drwxr-xr-x 1 kv 197121 0 Aug  9 21:51 .git/
-rw-r--r-- 1 kv 197121 9 Aug  9 21:18 README.md

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ cat > bug_report_str.txt
1. Number
2. Severity
3. Priority
4. Title
5. Environment
6. Precondition
7. Steps to reproduce (STR)
8. Expected result (ER)
9. Actual result (AR)
10. Attachment (link to video)
11. Postcondition (optional)

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ ls -la
total 14
drwxr-xr-x 1 kv 197121   0 Aug  9 21:52 ./
drwxr-xr-x 1 kv 197121   0 Aug  9 21:30 ../
drwxr-xr-x 1 kv 197121   0 Aug  9 21:51 .git/
-rw-r--r-- 1 kv 197121   9 Aug  9 21:18 README.md
-rw-r--r-- 1 kv 197121 208 Aug  9 21:52 bug_report_str.txt
```

## 4. Push the bug report structure to the remote repository
```
kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git add .
warning: in the working copy of 'bug_report_str.txt', LF will be replaced by CRLF the next time Git touches it

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git add .

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git commit -m "added bug_report_structure"
[Bug_Reports 22ebb9a] added bug_report_structure
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename bug_report_str => bug_report_str.txt (100%)

kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git status
On branch Bug_Reports
nothing to commit, working tree clean

??? (kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git push
fatal: The current branch Bug_Reports has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin Bug_Reports

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.)


kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git push origin Bug_Reports
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 970 bytes | 161.00 KiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Veronika-Koronets/Git_HW2.git
   c5a306a..22ebb9a  Bug_Reports -> Bug_Reports
```

## 5. Merge Bug Reports branch into main
```
kv@kvPC MINGW64 /d/Git_HW2 (Bug_Reports)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git merge Bug_Reports
Updating c5a306a..22ebb9a
Fast-forward
 bug_report_str.txt | 11 +++++++++++
 1 file changed, 11 insertions(+)
 create mode 100644 bug_report_str.txt
```

## 6. Push main to the remote repository

```
kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git push
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Veronika-Koronets/Git_HW2.git
   c5a306a..22ebb9a  main -> main
```

## 7. In the Checklists branch, create a document with checklist structure.

```
kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git checkout CheckLists
Switched to branch 'CheckLists'

kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ vim BRstr.txt

kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ cat BRstr.txt
1. Number
2. Severity
3. Priority
4. Title
5. Environment
6. Precondition
7. Steps to reproduce (STR)
8. Expected result (ER)
9. Actual result (AR)
10. Attachment (link to video)
11. Postcondition (optional)
```

## 8. Push this checklist structure to the remote repository

```
kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git add BRstr.txt
warning: in the working copy of 'BRstr.txt', LF will be replaced by CRLF the next time Git touches it

kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git add BRstr.txt

kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git commit -m "added BRstr.txt"
[CheckLists b5bcac5] added BRstr.txt
 1 file changed, 12 insertions(+)
 create mode 100644 BRstr.txt

???( kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git push
fatal: The current branch CheckLists has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin CheckLists

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.)


kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git push origin CheckLists
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 440 bytes | 55.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Veronika-Koronets/Git_HW2.git
   c5a306a..b5bcac5  CheckLists -> CheckLists
```

## 9. In the remote repository, do a pull request of Checklists branch into main
## 10. Synchronize remote and local main branches

```
kv@kvPC MINGW64 /d/Git_HW2 (CheckLists)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (2/2), 752 bytes | 68.00 KiB/s, done.
From https://github.com/Veronika-Koronets/Git_HW2
   22ebb9a..cd03d90  main       -> origin/main
Updating 22ebb9a..cd03d90
Fast-forward
 BRstr.txt | 12 ++++++++++++
 1 file changed, 12 insertions(+)
 create mode 100644 BRstr.txt

kv@kvPC MINGW64 /d/Git_HW2 (main)
$ ls -la
total 15
drwxr-xr-x 1 kv 197121   0 Aug  9 23:09 ./
drwxr-xr-x 1 kv 197121   0 Aug  9 21:30 ../
drwxr-xr-x 1 kv 197121   0 Aug  9 23:09 .git/
-rw-r--r-- 1 kv 197121 221 Aug  9 23:09 BRstr.txt
-rw-r--r-- 1 kv 197121   9 Aug  9 21:18 README.md
-rw-r--r-- 1 kv 197121 219 Aug  9 23:09 bug_report_str.txt
```
