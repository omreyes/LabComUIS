# Setting Up SSH for GitHub Repositories

This method uses **SSH keys**, which is more secure than tokens and avoids entering credentials repeatedly.

## Step 1: Generate an SSH Key (if not created)
1. Open a terminal (Ctrl + Alt + T) and generate a new SSH key:
   ```bash
   ssh-keygen -t ed25519 -C "your-email@example.com"
   ```
2. Press **Enter** to save it in `~/.ssh/id_ed25519` and set a passphrase if desired.

## Step 2: Add the SSH Key to GitHub
1. Copy your public key:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
2. Go to **GitHub → Settings → SSH and GPG keys → New SSH Key**.
3. Paste the copied key and save.

## Step 3: Test the SSH Connection
Run:
```bash
ssh -T git@github.com
```
If successful, you’ll see a message like:
```plaintext
Hi your-username! You've successfully authenticated, but GitHub does not provide shell access.
```

## Step 4: Set your Identity in the Local Machine

The first thing you should do before using Git in a local machine is to set your user name and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating. Run:
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
**NOTE:** you need to do this only once if you pass the --global option, because then Git will always use that information for anything you do on that system. If you want to override this with a different name or email address for specific projects, you can run the command without the --global option when you’re in that project.

## Step 5: Clone the Repository Using SSH
```bash
git clone git@github.com:your-username/your-repo.git
```

---

# What if a Collaborator Wants to Clone the Repo?
The process is the same, but they must have **proper access**:

1. The collaborator must be **added as a collaborator** in the repository settings on GitHub.
2. They should **generate their own SSH key** and add it to GitHub following the same steps above.
3. Once their SSH key is added, they can clone the repository with:
   ```bash
   git clone git@github.com:your-username/your-repo.git
   ```
