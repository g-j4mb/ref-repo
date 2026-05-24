# Setup and Configuration

## Set your identity globally
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

### Set default branch name to main
git config --global init.defaultBranch main

\# Check all configuration settings
git config --list

# Initializing and Cloning Projects

\# Turn an existing local directory into a Git repository
git init

\# Clone a remote repository over HTTPS or SSH
git clone https://github.com

# Tracking Changes (The Basics)


\# Check the status of your files (untracked, modified, staged)
git status

\# Give a compact, one-line status summary
git status -s

\# Stage a specific file for the next commit
git add file.java

\# Stage all modified and new files in the project
git add .

\# Unstage a file but keep its local modifications
git reset HEAD file.java

\# Save your staged snapshot permanently to history
git commit -m "Your commit message"

\# Stage all tracked files and commit them in one step
git commit -am "Your commit message"

# Examining History and Differences

\# View the commit history list
git log

\# View a clean, single-line graphic timeline graph
git log --oneline --graph --decorate

\# Show variations between your working directory and your staging area
git diff

\# Show variations between your staged files and your last commit
git diff --staged

\# View the metadata and code changes of a specific commit
git show <commit-hash>

# Branching and Merging

/# List all local branches (active branch has an asterisk)
git branch

/# List both local and remote-tracking branches
git branch -a

/# Create a new branch structure
git branch feature-name

/# Switch your working directory to an existing branch
git checkout branch-name

/# Create a new branch and switch to it immediately
git switch -c feature-name

/# Safe merge: Combine changes from 'feature-name' into your active branch
git merge feature-name

/# Force delete a local branch (must be switched off it first)
git branch -D feature-name


# Rebase and History Rewriting

/# Catch up feature branch by replaying commits on top of main
git rebase main

/# Abort an active rebase operation and restore original state
git rebase --abort

/# Continue rebase execution after resolving a code conflict
git rebase --continue

/# Clean up local history by squashing or renaming the last 3 commits
git rebase -i HEAD~3

/# Modify the message of your very last local commit
git commit --amend -m "New updated message"

# Remote Repository Synchronization

/# View configured remote servers and their target URLs
git remote -v

/# Link your local repository to a remote server
git remote add origin https://github.com

/# Download tracking data from remote without altering local files
git fetch origin

/# Download remote updates and merge them into your active branch
git pull origin main

/# Download remote updates using a clean, linear rebase strategy
git pull --rebase origin main

/# Upload local commits to remote server and set default tracking upstream
git push -u origin main

/# Safely upload rebased commits without overwriting teammate updates
git push --force-with-lease

# Undoing Mistakes and Resetting

/# Discard local changes in a specific file (revert to last commit)
git checkout -- file.java

/# Soft Reset: Move branch pointer back; keep your modified code staged
git reset --soft HEAD~1

/# Mixed Reset: Move branch pointer back; unstage changes but keep local files
git reset HEAD~1

/# Hard Reset: Wipe out the last commit and permanently delete all file edits
git reset --hard HEAD~1

/# Safe Revert: Create a brand new commit that completely mirrors the inverse of an old commit
git revert <commit-hash>

# Temporary Storage (Stashing)

/# Save modified, tracked files to a temporary shelf and clean your workspace
git stash

/# List all saved stashes in your workspace stack
git stash list

/# Re-apply your last stashed changes and remove it from the shelf
git stash pop

/# Re-apply your last stashed changes but keep it on the shelf
git stash apply

/# Permanently destroy all saved stashes on your shelf
git stash clear

# Advanced Diagnostics and Housekeeping

/# Search files for specified strings or patterns across history
git grep "Todo:"

/# Find the commit that introduced a bug using binary search
git bisect start
git bisect bad                  # Mark current version broken
git bisect good <commit-hash>   # Mark an older version functional

/# Recover lost commits or broken actions by viewing your HEAD tracking history
git reflog

/# Optimize repository database storage and delete unreachable junk files
git gc --prune=now


# issues
/# remote: error: GH007: Your push would publish a private email address.
git config --global user.email "ID+username@users.noreply.github.com"
git commit --amend --reset-author --no-edit
git push -u origin main
