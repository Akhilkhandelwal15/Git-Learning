```bash
# git commands

git --version
git init
git config --global user.email "<useremail>"
git config --global user.name "<username>"
git config --global core.editor "code --wait"
git log
git log --oneline
git status
git add .
git add <file_name1> <file_name2>
git commit -m "<commit_message>"
git commit -am "<commit_message>" : To add and commit at same time
git branch
git branch <branch_name>
git checkout <branch_name> : to switch to different branch
git switch <branch_name> : to switch to different branch
git checkout -b <branch_name> : create a new branch and switch to that branch
git switch -c <branch_name> : create a new branch and switch to that branch
git branch -d <branch_name> : To delete a branch
git diff : difference between file before changes and file after changes
git diff --staged : difference between unstaged file and staged version of same file 
git diff <commit_id_1> <commit_id_2> : difference between commit_id_1 and commit_id_2 version of file
git diff <commit_id_1>..<commit_id_2> : difference between commit_id_1 and commit_id_2 version of file (same as above)
git diff <branch_1>..<branch_2>
git stash : You’re in the middle of work, need to switch branches — stash it, come back later. Save your changes temporarily without committing them.
git stash pop :  Applies stash and deletes it: brings changes back & deletes from stash (if i stash some changes on one branch then I can pop those changes on other branch too)
git stash list : Shows the list of all saved stashes
git stash apply : Applies stash but keeps it
git stash apply <stash_id> : Apply a specific stash
git stash pop <stash_id> : Apply and delete a specific stash
git stash drop <stash_id> : delete a specific stash
git checkout <commit_id> : to get back to a specific commit
git reflog:	Show HEAD history (undo timeline)
git restore index.html :	Discard local changes in index.html
git checkout HEAD :	Restore all files to latest commit
git checkout HEAD~2 : Move to the commit 2 steps before current one
git rebase: Use with caution. Never use it when you are in main or master branch.
git branch -M <branch_name> : to rename the branch
git clone <url> : To bring a remote repository to local (Our system)
git fetch : Downloads remote changes but does not apply them
git pull: (git fetch + git merge) : Downloads and merges remote changes into current
git pull origin main: Get the latest changes from the main branch of the remote repository named origin and merge them into your current local branch.


#detailed explanation of git pull and git fetch:

git fetch <remote_name>
Downloads new data (commits, branches, tags) from the remote repository.
Does not automatically merge those changes into your local branch.
You can review the fetched changes before applying them.
Useful when you want to inspect changes before integrating them.

git pull <remote_name> <branch_name>
It is equivalent to:
git fetch + git merge
It downloads new changes from the remote and automatically merges them into your current branch.
Use it when you are ready to bring remote changes into your local working branch.
Can lead to merge conflicts if your local branch has diverged from the remote.


#github related commands

git remote -v : Shows the list of remote repositories and their URLs (for fetch & push).
git remote add <romote_name> <url> : Adds a new remote repository with the given name and URL.
git remote add origin https://guthub.com/akhilkhandelwal/repo.git : Example of above (Adds a remote named origin pointing to your GitHub repo.)
git remote <oldname> <newname> : Renames an existing remote from oldname to newname
git remote remove name : Removes the specified remote repository from your config.

git push <remote_name> <branch_name>
git push origin main 
git push -u origin main : here -u stand for upstream that allows you to run future command. if  i set upstream once while pushing then I can directly push in the main branch by simply tun "git push" no need to set origin and branch again and again


#additional commands:

touch <file_name> : to create a new file (multiple can be created)
mkdir <directory_name> : to create a new directory (multiple can be created)


# git diff Examples:

$ git diff
diff --git a/header.html (file before changes) b/header.html(file after changes)
index 9db1d0f..aa58929 100644
--- a/header.html (file before changes)
+++ b/header.html(file after changes)
@@ -4,8 +4,8 @@
    <li>Home</li>
    <li>Products</li>
    <li>Contact</li>
-   <li>About</li> (before)
-   <li>Logout</li> (before)
+   <li>About Us</li> (after)
+   <li>Logout Button</li> (after)


$ git diff --staged
index 9db1d0f..aa58929 100644
--- a/header.html (before stage)
+++ b/header.html (after stage)
@@ -4,8 +4,8 @@
    <li>Home</li>
    <li>Products</li>
    <li>Contact</li>
-   <li>About</li> (before stage)
-   <li>Logout</li> (before stage)
+   <li>About Us</li> (after stage)
+   <li>Logout Button</li> (after stage)


$ git diff 73a815f a60f6c6 or $ git diff 73a815f..a60f6c6
diff --git a/header.html (file on commit id 73a815f) b/header.html (file on commit id a60f6c6)
index 9db1d0f..aa58929 100644
--- a/header.html
+++ b/header.html
@@ -4,8 +4,8 @@
    <li>Home</li>
    <li>Products</li>
    <li>Contact</li>
-   <li>About</li> (on 73a815f)
-   <li>Logout</li> (on 73a815f)
+   <li>About Us</li> (on a60f6c6)
+   <li>Logout Button</li> (on a60f6c6)


# additonal commands and description

git reflog:
Shows a history of all changes to HEAD — even if you have moved branches or deleted commits.
Think of it like a "Git undo history".

git restore <file_name>:
Restores the working directory copy of a particular file from the latest commit. Use this if you changed the file but want to discard the changes.

git checkout HEAD:
Restores all files in the working directory to the last committed state (HEAD). Useful for discarding all uncommitted changes.

git checkout HEAD~2:
Checks out the commit that is 2 steps before HEAD. Moves your working directory to that previous commit. Be careful — this puts you in a detached HEAD state (you’re not on any branch). Use git switch <branch> to go back to a branch later.

git rebase: 
To avoid messy merge commits  
To keep history clean and linear  
To update your feature branch with the latest changes from main/master
