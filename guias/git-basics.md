# Git Branching Basics for Collaboration

This guide explains how two collaborators can use branches in a GitHub repository to contribute and keep everything up to date.

## Step 1: Clone the Repository
```bash
git clone git@github.com:your-username/your-repo.git
cd your-repo
```

## Step 2: Create a New Branch
```bash
git checkout -b feature-branch
```
Replace `feature-branch` with a descriptive name for your feature or fix.

## Step 3: Make Changes and Commit
1. Edit or add files.
2. Stage the changes:
   ```bash
   git add .
   ```
3. Commit the changes:
   ```bash
   git commit -m "Add feature description"
   ```

## Step 4: Push the Branch to GitHub
```bash
git push origin feature-branch
```

## Step 5: Create a Pull Request (PR)
1. Go to the repository on GitHub.
2. Click **Compare & pull request**.
3. Add details and submit the PR.

## Step 6: Review and Merge
- A collaborator reviews the PR.
- Once approved, merge the branch.

## Step 7: Update Local Repository
After merging, keep your local repository updated:
```bash
git checkout main
git pull origin main
git branch -d feature-branch
```

Now both collaborators can work efficiently with branches! 🚀

