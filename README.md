# GIT Assignment

### Q.1) You have made changes to multiple files in your Git repository and want to stage and commit these changes. What commands would you use to stage all the changes and commit them with a meaningful commit message?
```bash
git add .
git commit -m "commit message"
```

### Q.2) You have committed changes to a wrong branch. How would you move these commits to the correct branch?
```bash
# Step 1: Save the commits using temporary branch
git checkout -b temp-branch       # Create a temp branch with the commits

# Step 2: Switch back to the wrong branch and reset it
git checkout wrong-branch
git reset --hard HEAD~n           # n = number of commits to remove

# Step 3: Switch to the correct branch and merge the temp branch
git checkout correct-branch
git merge temp-branch

# Step 4: Delete the temporary branch
git branch -d temp-branch
```

### Q.3) You want to create a new branch, make changes, and push the branch to the remote repository. Outline the steps you would take to create a new branch, commit changes, and push the branch to GitHub.
```bash
git checkout -b feature-branch-name       # Create and switch to new branch
# Make your changes...
git add .                                 # Stage changes
git commit -m "Added new feature"         # Commit changes
git push origin feature-branch-name       # Push to GitHub
```

### Q.4) You want to contribute to an open-source project hosted on GitHub. What are the steps you would follow to fork the repository, make changes, create a pull request, and collaborate with the original project?
```bash
# clone repo
git clone https://github.com/ommore86/projectname.git
cd projectname

# add the original repo as upstream
git remote add upstream https://github.com/mark1998/projectname.git

# create new branch for feature
git checkout -b feature-branch

# commit
git add .
git commit -m "Changed XYZ feature"
git push origin feature-branch
```

### Q.5) You are working on a team project, and there are conflicts between your branch and the main branch. How would you resolve these merge conflicts? Provide the necessary commands and steps.
```bash
# To check the conflicts
git checkout your-branch
git pull origin main               # Merge main into your branch

# To resolve the conflicts
git add .
git commit
```

### Q.6) You want to create a feature branch based on the latest changes in the main branch. What commands would you use to create a new branch and automatically switch to it, ensuring it's up to date with the latest changes from the main branch?
```bash
git checkout main
git pull origin main              # Make sure local main is up to date
git checkout -b feature-branch    # Create and switch to new branch
```

### Q.7) You have made a series of commits, but you realize that a change made several commits ago is causing issues in your application. How would you revert to a specific commit, discarding all changes made after that commit?
```bash
git reset --hard <commit-hash>     # WARNING: This discards all commits after the given hash
```

### Q.8) You have accidentally deleted a file in your Git repository and committed the change. What commands would you use to restore the deleted file from the previous commit?
```bash
# If you have commited
git checkout HEAD~1 -- <path/to/file>
git add <path/to/file>
git commit -m "Restored accidentally deleted file"

# If you haven't commited
git checkout -- <path/to/file>
```
