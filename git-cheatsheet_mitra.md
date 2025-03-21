# Git Cheatsheet

## Git Areas
- **Working Directory:** Files currently being edited.
- **Staging Area (Index):** Files ready for commit (`git add`).
- **Local Repository:** Stored commit history.

---

## Branching & HEAD

| Action                      | Command                             |
|-----------------------------|-------------------------------------|
| Create & switch branch      | `git checkout -b feature/name`      |
| Switch branches             | `git checkout main`                 |
| Merge branch                | `git merge feature/name`            |
| Check current HEAD          | `cat .git/HEAD`                     |
| Inspect branch pointer      | `cat .git/refs/heads/main`          |
| List all branches           | `git branch`                        |

---

## Basic Commands

| Action                         | Command                            |
|--------------------------------|------------------------------------|
| Clone repository               | `git clone <repo_url>`             |
| Initialize local repository    | `git init`                         |
| Stage files                    | `git add file.txt`                 |
| Commit files                   | `git commit -m "message"`          |
| Push commits                   | `git push origin main`             |
| Pull updates                   | `git pull origin main`             |
| Check status                   | `git status`                       |
| View history                   | `git log --oneline --stat`         |
| Amend last commit              | `git commit --amend`               |

---

## Undo & Restore

| Action                              | Command                             |
|-------------------------------------|-------------------------------------|
| Undo last commit, keep changes      | `git reset --soft HEAD~1`           |
| Completely undo last commit         | `git reset --hard HEAD~1`           |
| Undo uncommitted file changes       | `git checkout -- file.txt`          |
| Restore deleted file                | `git restore file.txt`              |
| Safe revert commit                  | `git revert <commit_hash>`          |
| Diff current state vs last commit   | `git diff HEAD`                     |
| Diff working directory vs staging   | `git diff`                          |
| Diff staging vs last commit         | `git diff --cached`                 |
| Show commit contents                | `git show HEAD~1:file.txt`          |
| Full SHA-1 of last commit           | `git rev-parse HEAD`                |
| SHA-1 of file                       | `git hash-object file.txt`          |

### Advanced Reset

| Command                         | Effect                                     |
|---------------------------------|--------------------------------------------|
| `git reset --soft <commit>`     | Moves HEAD, retains index & working tree   |
| `git reset --mixed <commit>`    | Moves HEAD, resets index, retains changes  |
| `git reset --hard <commit>`     | Moves HEAD, resets index and working tree  |

---

## Rebase & Merge

| Action                  | Command                                 |
|-------------------------|-----------------------------------------|
| Merge branch            | `git merge branch_name`                 |
| Rebase current branch   | `git rebase branch_name`                |
| Resolve merge conflict  | Manually edit file, `git add`, `git commit` |
| Merge tool (graphical)  | `git mergetool`                         |

---

## Remote Repositories

| Action                 | Command                         |
|------------------------|---------------------------------|
| View remotes           | `git remote`                    |
| View remotes (verbose) | `git remote -v`                 |
| Add remote             | `git remote add origin <URL>`   |
| Push changes           | `git push origin main`          |
| Fetch remote changes   | `git fetch origin`              |

---

## Ancestry References
- `HEAD~n`: nth generation ancestor (e.g., `HEAD~1`)
- `HEAD^`: first parent commit
- `HEAD^^`: second parent commit (merge commits)
- `@`: Alias for `HEAD`
- Reflog: `git reflog` (recover lost commits)

---

## Temporary Saving (Stash)

| Action                       | Command                        |
|------------------------------|--------------------------------|
| Stash current changes        | `git stash`                    |
| List stashes                 | `git stash list`               |
| Apply last stash             | `git stash apply`              |
| Drop last stash              | `git stash drop`               |
| Apply and drop last stash    | `git stash pop`                |

---

## Jupyter Notebooks & Git
- Clear outputs before commit: `Jupyter -> Edit -> Clear All Outputs`
- Tools: `nbstripout`, `nbdime`

---

## GitHub Gists
- Lightweight code snippets with Git functionality
- Useful for sharing and embedding code quickly
- Accessible via browser, version-controlled

---

## Repo Best Practices
Include in repository:
- **LICENSE** (permissions and restrictions)
- **README.md** (description, setup guide, contribution info)
- **CITATION** (how to cite the project)

---

## Resources
- [VS Code Git Docs](https://code.visualstudio.com/docs/sourcecontrol/overview)
- [Pro Git Book](https://git-scm.com/book)
- [Ten Simple Rules for Taking Advantage of Git and Github](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004947)
- [GitHub Training Kit](https://github.com/github/training-kit)
- [Recommended Repositories](https://journals.plos.org/plosone/s/recommended-repositories)
- [NBConvert Tool: converts jupyter notebooks to various other formats](https://github.com/jupyter/nbconvert)