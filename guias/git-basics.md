# Git Branching Basics for Collaboration

This guide explains how two collaborators can use branches in a GitHub repository to contribute and keep everything up to date.

# Git Branching Basics for Collaboration

## Summary of Workflow
1. One collaborator creates a new branch from `main`, e.g., `practise1`.
2. Each collaborator creates their own branch from `practise1` (e.g., `practise1-devA`, `practise1-devB`).
3. Work on changes, commit, and push to GitHub.
4. Open a Pull Request (PR) to merge into `practise1`.
5. Review and merge the PR.
6. Update `practise1` locally and continue working on new branches if needed.
7. Once all work is completed, merge `practise1` into `main`.

## Step 1: Clone the Repository Using SSH
(see [Setting Up SSH for GitHub Repositories](https://github.com/omreyes/LabComUIS/blob/main/guias/create-repository.md) for details about generation of SSH Keys)
```bash
git clone git@github.com:your-username/your-repo.git
cd your-repo
```

## Step 2: Create a New Branch
One collaborator creates a new branch from `main`:
```bash
git checkout -b practise1
```
Push the new branch to GitHub:
```bash
git push origin practise1
```

## Step 3: Each Collaborator Creates a Branch
Each collaborator creates their own branch from `practise1`:
```bash
git checkout -b practise1-devA  # Developer A
# OR
git checkout -b practise1-devB  # Developer B
```
Push to GitHub:
```bash
git push origin practise1-devA  # Developer A
# OR
git push origin practise1-devB  # Developer B
```

## Step 4: Make Changes and Commit
1. Edit or add files.
2. Stage the changes:
   ```bash
   git add .
   ```
3. Commit the changes:
   ```bash
   git commit -m "Add feature description"
   ```

## Step 5: Open a Pull Request (PR)
- When a collaborator finishes their changes, they open a **Pull Request (PR)** to merge into `practise1`.
- On GitHub, navigate to **Pull Requests → New Pull Request**.
- Compare `practise1-devA` or `practise1-devB` with `practise1`, add details, and submit the PR.

## Step 6: Review and Merge
- Collaborators review the PR and request changes if necessary.
- Once approved, merge the PR into `practise1`.
- After merging, update `practise1` locally:
  ```bash
  git checkout practise1
  git pull origin practise1
  ```

## Step 7: Merging into Main
Once all work is completed and tested, merge `practise1` into `main`:
```bash
git checkout main
git merge practise1
git push origin main
```

## Step 8 (Optional): Keep or Delete Developer Branches
After merging, decide whether to keep or delete the developer branches:
- To delete a local branch:
  ```bash
  git branch -d practise1-devA
  git branch -d practise1-devB
  ```
- To delete a remote branch:
  ```bash
  git push origin --delete practise1-devA
  git push origin --delete practise1-devB
  ```
