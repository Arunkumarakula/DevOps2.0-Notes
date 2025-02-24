## Git Commands

### 1. Initialize a Git Repository
- `git init` : Initializes a new empty Git repository in the current directory by creating a hidden `.git` folder to track changes and store history.

### 2. Clone a Repository
- `git clone <repo-url>` : Creates a copy of an existing Git repository, including all files, history, and branches.

### 3. Configure Git User
- `git config --global user.name "username"` : Sets your name for all commits across repositories.
- `git config --global user.email "email@example.com"` : Sets your email address for all commits across repositories.
- `git config --global user.name` : Displays the configured username.
- `git config --global user.mail` : Displays the configured email ID.
- `git config --global --list` : Lists all configured Git user details.

### 4. Staging and Committing Changes
- `git add <file-name>` : Stages a file for commit.
- `git commit -m "message"` : Commits all staged files with a message.
- `git commit -m "message" <filename>` : Commits changes for a specific file.
- `git commit -am "message"` : Commits changes directly, skipping `git add` (only for tracked files).
- `git commit --amend -m "message"` : Modifies the most recent commit message.
- `git commit --amend --author "username <email>"` : Changes the author of the latest commit.

### 5. Checking Status and Logs
- `git status` : Displays the state of the working directory and staged changes.
- `git log` : Displays commit history with details like commit ID, user details, and timestamp.
- `git log --oneline` : Displays a compact commit history (7-character commit ID).
- `git log --1` : Displays the most recent commit ID.
- `git reflog` : Shows the history of all branches.

### 6. Viewing and Comparing Changes
- `git diff` : Compares working directory changes.
- `git diff <commit-id>` : Shows differences between a specific commit and the working directory.
- `git diff <commit-id>..<commit-id>` : Compares changes between two commits.

### 7. Working with Branches
- `git branch` : Lists all branches and highlights the current branch.
- `git branch <branch-name>` : Creates a new branch.
- `git checkout -b <branch-name>` : Creates and switches to a new branch.
- `git checkout <branch-name>` : Switches to another branch.
- `git switch <branch-name>` : Alternative command for switching branches.
- `git branch -m <old-name> <new-name>` : Renames a branch.
- `git branch -d <branch-name>` : Deletes a branch.
- `git branch -D <branch-name>` : Force deletes a branch.
- `git branch -a` : Lists all local and remote branches.
- `git branch -r` : Lists only remote branches.

### 8. Merging and Reverting Changes
- `git merge <branch-name>` : Merges a branch into the current branch.
- `git merge --abort` : Cancels a merge when conflicts arise.
- `git cherry-pick <commit-id>` : Applies a specific commit from another branch without merging the entire branch.
- `git revert <commit-id>` : Undoes a commit by creating a new commit that negates the changes.
- `git revert HEAD --no-edit` : Reverts the latest commit without opening the commit message editor.

### 9. Restoring Changes
- `git restore <file-name>` : Unstages a file from the staging area without discarding changes.
- `git restore <deleted-file>` : Restores a deleted file.
- `git stash` : Temporarily saves changes that are not ready to be committed.
- `git stash list` : Displays all stashed changes.
- `git stash pop` : Removes and applies the most recent stash.
- `git stash drop` : Deletes the most recent stash.
- `git stash clear` : Clears all stashes.
- `git stash apply stash@{0}` : Applies a specific stash.
- `git stash drop stash@{1}` : Removes a specific stash.

### 10. Working with Remote Repositories
- `git remote add origin <repo-url>` : Links a local repository to a remote repository.
- `git remote rm origin` : Unlinks a remote repository.
- `git fetch <branch-name>` : Fetches updates from a remote branch.
- `git fetch --all` : Fetches updates from all branches.
- `git pull <branch-name>` : Fetches and merges changes from a remote branch.
- `git push <remote> <branch>` : Pushes local commits to a remote repository.
- `git push -u origin <branch-name>` : Pushes a new branch to a remote repository for the first time.
- `git push -u origin branch1 branch2` : Pushes multiple branches at the same time.
- `git push -u origin --all` : Pushes all branches to the remote repository.
- `git push -u origin --delete <branch-name>` : Deletes a remote branch.

### 11. Miscellaneous Commands
- `git --version` : Displays the installed Git version.
- `which git` : Shows the Git installation path.
- `git help --all` : Lists all available Git commands.
- `git add --all` : Stages all changes in the current folder.
- `.gitignore` : Specifies files and directories to ignore in Git.
- `rm -rf .git` : Removes the Git repository from the current directory.

### 12. .gitignore Examples
- `*.temp` : Ignores all `.temp` files.
- `temp/` : Ignores all files inside any directory named `temp`.
- `temp?.log` : Ignores `temp1.log`, `temp2.log`, `temp3.log`, etc.

