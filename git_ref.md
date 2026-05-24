# Setup and Configuration

\# Set your identity globally
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

\# Set default branch name to main
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

