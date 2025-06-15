#git commands

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
git commit -am "<commit_message>"   # To add and commit at same time
git branch
git branch <branch_name>
git checkout <branch_name>         # to switch to different branch
git switch <branch_name>           # to switch to different branch
git checkout -b <branch_name>      # create a new branch and switch to that branch
git switch -c <branch_name>        # create a new branch and switch to that branch
git branch -d <branch_name>        # To delete a branch
git diff                           # difference between file before changes and file after changes
git diff --staged                  # difference between unstaged file and staged version of same file 
git diff <commit_id_1> <commit_id_2>        # difference between commit_id_1 and commit_id_2 version of file
git diff <commit_id_1>..<commit_id_2>       # same as above
git diff <branch_1>..<branch_2>
git stash                          # Save your changes temporarily without committing them.
git stash pop                      # Applies stash and deletes it (can pop on other branches too)
git stash list                     # Shows the list of all saved stashes
git stash apply                    # Applies stash but keeps it
git stash apply <stash_id>        # Apply a specific stash
git stash pop <stash_id>          # Apply and delete a specific stash
git stash drop <stash_id>         # Delete a specific stash
git checkout <commit_id>          # To get back to a specific commit
git reflog                         # Show HEAD history (undo timeline)
git restore index.html             # Discard local changes in index.html
git checkout HEAD                  # Restore all files to latest commit
git checkout HEAD~2                # Move to the commit 2 steps before current one
git rebase                         # Use with caution. Never use it when you are in main or master branch.
git branch -M <branch_name>        # to rename the branch


#github related commands

git remote -v                            # Shows the list of remote repositories and their URLs (for fetch & push).
git remote add <remote_name> <url>       # Adds a new remote repository with the given name and URL.
git remote add origin https://github.com/akhilkhandelwal/repo.git   # Example
git remote <oldname> <newname>           # Renames an existing remote from oldname to newname
git remote remove name                   # Removes the specified remote repository from your config.

git push <remote_name> <branch_name>
git push origin main 
git push -u origin main                  # -u = upstream, allows you to run future `git push` without args


#additional commands

# Git & GitHub Commands Guide

## 📁 Additional Commands:

```bash
touch <file_name>          # to create a new file (multiple can be created)
mkdir <directory_name>     # to create a new directory (multiple can be created)


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
Shows a history of all changes to HEAD — even if you've moved branches or deleted commits.
Think of it like a "Git undo history".

git restore <file_name>:
Restores the working directory copy of a particular file from the latest commit.

git checkout HEAD:
Restores all files in the working directory to the last committed state (HEAD).

git checkout HEAD~2:
Checks out the commit that is 2 steps before HEAD. Puts you in detached HEAD state.

git rebase:
To avoid messy merge commits
To keep history clean and linear
To update your feature branch with the latest changes from main/master
