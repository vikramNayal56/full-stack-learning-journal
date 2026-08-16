 # Git & GitHub

Although Git and GitHub are often used together, they serve different purposes.

## Git vs GitHub

| Git | GitHub |
|------|---------|
| Version Control System | Cloud platform for Git repositories |
| Tracks changes locally | Hosts repositories online |
| Works without internet | Makes collaboration and sharing easier |

---

## Git Workflow

Whenever I worked on a project, my changes followed this workflow:

```text
Working Directory
        │
     git add
        │
        ▼
  Staging Area
        │
   git commit
        │
        ▼
 Local Repository
        │
    git push
        │
        ▼
     GitHub
```

---

## Common Git Commands

| Command | Purpose |
|----------|---------|
| `git init` | Initialize a repository |
| `git status` | Check repository status |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save a snapshot |
| `git push` | Upload commits to GitHub |
| `git pull` | Download latest changes |
| `git clone <url>` | Copy a repository |
| `git branch` | List or create branches |
| `git checkout <branch>` | Switch branches |
| `git merge` | Merge branches |

> **Tip:** Writing meaningful commit messages makes it easier to understand the project's history later.

---

# GitHub Pages

GitHub Pages allows static websites to be hosted directly from a GitHub repository.

## Steps

1. Push the project to GitHub.
2. Open **Repository Settings**.
3. Go to **Pages**.
4. Select the branch.
5. Save the settings.
6. GitHub generates a live website link.

---

# Markdown

Markdown is a lightweight language used for writing documentation.

I used Markdown to create README files because it is simple, readable, and supported by GitHub.

## Common Syntax

| Syntax | Output |
|---------|--------|
| `# Heading` | Heading |
| `**Text**` | **Bold** |
| `*Text*` | *Italic* |
| `` `code` `` | `code` |
| `- Item` | Bullet List |
| `1. Item` | Numbered List |

---

# Tools I Used

| Tool | Purpose |
|------|---------|
| VS Code | Writing and managing code |
| Chrome DevTools | Inspecting HTML, CSS, and Network requests |
| Git | Version control |
| GitHub | Hosting repositories |
| GitHub Pages | Hosting static websites |
| Dillinger | Writing and previewing Markdown |

---

# Key Learnings

- Understanding concepts is more important than memorizing syntax.
- Writing clean HTML makes CSS easier to manage.
- Git provides confidence to experiment because changes can always be tracked.
- Browser Developer Tools are essential for debugging.
- Building projects is the best way to strengthen fundamentals.
- Clean code, meaningful file names, and proper folder structure make projects easier to maintain.

---
## Quick Revision

- Git → Version control
- GitHub → Online repository hosting
- Commit → Snapshot of changes
- Push → Upload changes
- Pull → Download latest changes
- GitHub Pages → Host static websites
- Markdown → Documentation
---