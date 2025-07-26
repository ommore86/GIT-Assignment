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
git clone https://github.com/your-username/project-name.git
cd project-name
git remote add upstream https://github.com/original-owner/project-name.git
git checkout -b feature-branch
git add .
git commit -m "Brief description of changes"
git push origin feature-branch
```
