# jenkins

pull

C:\Users\prani\OneDrive\Desktop\pull>git init
Initialized empty Git repository in C:/Users/prani/OneDrive/Desktop/pull/.git/

C:\Users\prani\OneDrive\Desktop\pull>git remote add origin "https://github.com/pranittemkar23/regform.git"

C:\Users\prani\OneDrive\Desktop\pull>git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 1.09 KiB | 55.00 KiB/s, done.
From https://github.com/pranittemkar23/regform
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main

How to check git version?
$ git --version
git version 2.32.0.windows.1
Creating git repository:
DIPAK@DESKTOP-1VCFSFJ MINGW64 ~
$ mkdir mywebpage
DIPAK@DESKTOP-1VCFSFJ MINGW64 ~
$ cd mywebpage
DIPAK@DESKTOP-1VCFSFJ MINGW64 ~/mywebpage
$ git init
Initialized empty Git repository in
C:/Users/DIPAK/mywebpage/.git/
(path of git repository in our machine)
How to display the hidden folder in git
repository
$ ls -a
./ ../ .git/
Note: git folder is very imp once you deteted it whole
repository is deleted
How to set our identity to git repository?
$ git config --global user.email
pravin_patil@pvppcoe.ac.in
$ git config --global user.name pravin
How to configure gedit to git?
$ git config --global core.editor gedit
--global Flag?
● Multiple repositories can be created in
single machine
● If we use --global flag then setting will be
applied to all the repositories of the
machine
● If you want his identity for particular
repository then don not use --global flag.
How to check the configuration details of
identity set earlier?
$ git config --list
user.email=pravin_patil@pvppcoe.ac.in
user.name=pravin
core.editor=gedit
How to ask to git to follow the page?
$ nano abc.txt & file created
$ git add abc.txt
$ git status called tracking git following abc.txt file
On branch master
No commits yet
Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: abc.txt
Go to the file add few lines and close the file and
switch back to terminal
$ git status
On branch master
No commits yet
Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: abc.txt
Changes not staged for commit:
(use "git add <file>..." to update what will be
committed)
(use "git restore <file>..." to discard changes in
working directory)
modified: abc.txt
Note: Changes has not been added to staged area
Staging area:
● Staging area is a file that store information of
changes that need to be commit.
● The file content should be added to staging area
before commit them.
● Older version of git used term index instead of
staging area.
$git add abc.txt used to staged changes
$ git status
On branch master
No commits yet
Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: abc.txt
Note: changes are added to staged area.
How to commit?
$git commit (nano editor automatically opened
to get commit message)
[master (root-commit) 37640c4] Initil Commit
1 file changed, 2 insertions(+)
create mode 100644 abc.txt
How to get commit details?
$ git log
commit 37640c44da28347658605b315e5c91100ecf9ad0 (HEAD
-> master)
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Tue Jun 29 15:26:54 2021 +0530
Initil Commit
Note: only 1 commit in our repository
Each commit has unique id called commit
hash or SHA-1 hash
SHA-1 hash:
● Unique id of 40 digit alpha-numerical
characters
● Git store all its info using hash value into
the database.
● Git commits are identified using SHA-1 hash.
Assignment 2
How to create multiple files in nano editor?
$ nano myschool.text mycollege.text
$ ls -a
./ ../ .git/ mycollege.text myschool.text
$ git status
On branch master
No commits yet
Untracked files:
(use "git add <file>..." to include in what will be
committed)
mycollege.text untracked files
myschool.text
nothing added to commit but untracked files present
(use "git add" to track)
How to add untracked file for tracking or in staged
area?
$git add . used to add all untracked
files in staged area
Note: using add . Command untracked fill will be
tracked and added to staging area.
$ git status
On branch master
No commits yet
Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: mycollege.text file are added
to staged area
new file: myschool.text
Add few statement in file and save it and close.
The execute status command
$ git status
On branch master
No commits yet
Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: mycollege.text
new file: myschool.text
Changes not staged for commit:
(use "git add <file>..." to update what will be
committed)
(use "git restore <file>..." to discard changes in
working directory)
modified: mycollege.text
modified: myschool.text
Note : Changed not added to staged area for
commit.
$ git commit -a -m "added 2 files"
warning: LF will be replaced by CRLF in mycollege.text.
The file will have its original line endings in your
working directory
warning: LF will be replaced by CRLF in myschool.text.
The file will have its original line endings in your
working directory
[master (root-commit) ea8e1bd] added 2 files
2 files changed, 6 insertions(+)
create mode 100644 mycollege.text
create mode 100644 myschool.text
Note :
-a flag used to add all modified file into
staged area no need to use add . command.
-m flag used to print commit message command
line itself e.g. “added 2 files”
We can use –am together
$ git log
commit ea8e1bd97737369303880b45de2479d9986d2b75 (HEAD
-> master)
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 12:39:52 2021 +0530
added 2 files
Note: Latest commits are listed first. Commits
are listed in chronological order.
How to remove file from staged area?
$ git rm --cached mycollege.text
rm 'mycollege.text'
Check the Status..
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
deleted: mycollege.text
Untracked files:
(use "git add <file>..." to include in what will be
committed)
mycollege.text
Note: Untracked means deteted from staged area.
How to deleted file form repository ?
$rm mycollege.text
$ ls
myschool.text
Note: file is completely deleted from file system.
Commit the delete activity
$ git commit -am "Deleted file mycollege.text"
[master 5f42cee] Deleted file mycollege.text
1 file changed, 3 deletions(-)
delete mode 100644 mycollege.text
Check the status..
$ git log
commit 5f42ceea35f40e495949a83274b61f4815f1c69f (HEAD
-> master)
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 14:35:08 2021 +0530
Deleted file mycollege.text
commit ea8e1bd97737369303880b45de2479d9986d2b75
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 12:39:52 2021 +0530
added 2 files
Note: latest commit with deletion operation is shown
with delete message.
How to restore by mistake deleted file?
We can restore the file by using previous commit.
$ git checkout ea8e1 mycollege.text
Updated 1 path from 6cae774
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
new file: mycollege.text
Note: file are restored in staged area.
Commit our restoring work…
Note: whenever we want to add or delete file then need
to commit our work.
$ git commit -am "restore mycollege.text"
[master 2a51697] restore mycollege.text
1 file changed, 3 insertions(+)
create mode 100644 mycollege.text
$ ls
mycollege.text myschool.text
using ls commit we will see our file might be restored.
How to discard the changes made to a file?
Add some statement or delete some statement from the
file and save and close.
Check the status of modification….
$ git status
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be
committed)
(use "git restore <file>..." to discard changes in
working directory)
modified: mycollege.text
modified: myschool.text
no changes added to commit (use "git add" and/or "git
commit -a")
$ git checkout .
Updated 2 paths from the index
Checkout . command used to discard the latest changes.
$ git status
On branch master
nothing to commit, working tree clean
Note:check the status nothing to commit Modification is
discarded now check the log
$ git log
commit 2a51697da1a38d67a653f4a64401a173a7f40a37 (HEAD
-> master)
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 14:50:27 2021 +0530
restore mycollege.text
commit 5f42ceea35f40e495949a83274b61f4815f1c69f
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 14:35:08 2021 +0530
Deleted file mycollege.text
commit ea8e1bd97737369303880b45de2479d9986d2b75
Author: pravin <pravin_patil@pvppcoe.ac.in>
Date: Wed Jun 30 12:39:52 2021 +0530
added 2 files
