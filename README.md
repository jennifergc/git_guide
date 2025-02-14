# Ultimate Guide to GIT for Ubuntu

## Created by Jennifer Grisales

### Description
This guide provides a step-by-step tutorial on how to install, configure, and use Git on Ubuntu. It includes essential commands and best practices for synchronizing local repositories with GitHub using SSH authentication.

### Features
- Installation instructions for Git on Ubuntu.
- Step-by-step guide for setting up SSH authentication with GitHub.
- Basic and advanced Git commands for version control.
- Explanation of Git branches, commits, and synchronization.
- Life hack for cloud-local synchronization using GitHub repositories.

### Basic Git Workflow
```sh
git status         # Check the repository status
git add -A        # Stage all changes
git commit -m "Commit message"  # Commit changes
git push -u origin main  # Push changes to remote repository
git pull          # Update local repository with remote changes
```

### Cloning a Repository
To clone a repository from GitHub:
```sh
git clone git@github.com:your_username/repository_name.git
```
### Branch Management
```sh
git branch feature-branch     # Create a new branch
git checkout feature-branch  # Switch to the new branch
git merge feature-branch     # Merge branch into main
git branch -d feature-branch  # Delete the branch
```

### Contributing
Feel free to improve this guide and share your knowledge by submitting a pull request!

### License
This project is licensed under the MIT License.
