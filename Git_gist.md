# Git/GitHub Integration in VS Code

See also the gist on [Github](https://gist.github.com/mitrazad/2f7fce727933f9c85f609b9168785557).

- Git is a **distributed version control system** for tracking and managing code changes. 
- GitHub provides cloud-based hosting of Git repositories, facilitating easy collaboration and tracking.
- Visual Studio Code (VS Code) offers powerful built-in Git integration, enhancing your workflow by allowing direct version control within the editor.

---

## Setting Up Git in VS Code

### 1. Install & Configure Git

Verify installation:
```bash
git --version
```

Configure user identity:
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

### 2. Authenticate with GitHub
- **HTTPS**: Generate a GitHub Personal Access Token (PAT).
- **SSH**: Generate an SSH key:
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Then add the generated public key (`~/.ssh/id_rsa.pub`) to your GitHub account under Settings -> SSH keys.

---

## Cloning a GitHub Repository

From Terminal:
```bash
git clone https://github.com/user/repo.git
```

From VS Code:
- Press `Ctrl+Shift+P` -> Select **"Git: Clone"** -> Paste URL -> Select folder.

---

## Basic Git Workflow

### Stage, Commit, and Push

Terminal commands:
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

In VS Code:
- Open **Source Control Panel** (`Ctrl+Shift+G`)
- Stage changes (**+**), write commit message, and press **Commit**.
- Click **Sync Changes** at the bottom to push. Or click at the three dots in the **Changes** panel -> Pull, Push -> Sync.

### Pull Updates
Terminal:
```bash
git pull origin main
```

VS Code:
- Click **Pull** button from Source Control Panel (**Graph** panel). 
- Or click at the three dots in the **Changes** panel -> Pull, Push -> Pull.

---

## Branch Management

### Create and Switch to a New Branch
Terminal:
```bash
git checkout -b feature/my-new-feature
```

VS Code:
- Click branch name at the bottom-left corner -> Select **"Create new branch"**. 
- Or click at the three dots in the **Changes** panel -> Branch -> Create Branch.

### Switch Between Existing Branches
Terminal:
```bash
git checkout branch-name
```

VS Code:
- Click branch name in bottom-left corner and select branch from list.

---

## Merge Branches

Merge branch `feature/my-new-feature` into `main`:
```bash
git checkout main
git merge feature/my-new-feature
```

VS Code:
- Click at the three dots in the **Changes** panel -> Branch -> Merge -> Select branch to merge from.
- Or resolve merge conflicts visually using VS Code's built-in 3-Way Merge Editor.

---

## Resolving Conflicts in VS Code with 3-Way Merge Editor

If conflicts occur after pulling or merging:
- Open conflicted file.
- Choose to accept current, incoming, or both changes.
- Save and stage the resolved file:
```bash
git add filename
git commit -m "Resolved merge conflict"
```

---

## Resources
- [VS Code Git Documentation](https://code.visualstudio.com/docs/sourcecontrol/overview)