# Assignment 1.4 — Solution: Git Essentials I

## 1. Install Git and verify
Download from https://git-scm.com (Windows/macOS) or use a package manager (`sudo apt install git` on Linux, `brew install git` on macOS). Then verify:
```bash
git --version
# git version 2.x.x
```

## 2. Open the terminal in the project folder
```bash
mkdir git-practice
cd git-practice
code .          # optional: open in VS Code and use its integrated terminal
```

## 3. Initialize the repository
```bash
git init
# Initialized empty Git repository in .../git-practice/.git/
```

## 4. Configure username and email
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Verify
git config --list
```
> Use the same email as your GitHub account.

## 5. Create an HTML file
```bash
touch index.html          # Windows cmd: type nul > index.html
```
Add to `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Git Practice</title>
  </head>
  <body>
    <h1>Hello, Git!</h1>
  </body>
</html>
```

## 6 & 7. `git status`, `git add`, `git commit` — three meaningful commits

### Commit 1 — Initial HTML structure
```bash
git status                      # index.html shows as untracked
git add index.html
git status                      # index.html is staged ("Changes to be committed")
git commit -m "Add initial HTML structure"
```

### Commit 2 — Add page content
Edit `index.html`, replacing the body with:
```html
  <body>
    <h1>Hello, Git!</h1>
    <p>This project is tracked with Git.</p>
    <ul>
      <li>git init</li>
      <li>git add</li>
      <li>git commit</li>
    </ul>
  </body>
```
```bash
git status                      # index.html shows as modified
git add index.html
git commit -m "Add paragraph and list of basic Git commands"
```

### Commit 3 — Add CSS styling
Create `style.css`:
```css
body {
  font-family: Arial, sans-serif;
  margin: 40px;
  background-color: #f4f4f4;
}
h1 {
  color: #2c3e50;
}
```
Link it in `<head>` of `index.html`:
```html
    <link rel="stylesheet" href="style.css" />
```
```bash
git status                      # style.css untracked, index.html modified
git add .
git commit -m "Add CSS styling and link stylesheet"
```

## View the history (for the screenshot)
```bash
git log
git log --oneline
```
Example output (hashes will differ):
```
c3a91f2 Add CSS styling and link stylesheet
8b47d0e Add paragraph and list of basic Git commands
1f5e6a9 Add initial HTML structure
```

## Command Summary
| Command | Purpose |
|---------|---------|
| `git --version` | Check Git is installed |
| `git init` | Create a new repository |
| `git config` | Set username/email |
| `git status` | Show changed/staged/untracked files |
| `git add <file>` / `git add .` | Stage changes |
| `git commit -m "msg"` | Save a snapshot with a message |
| `git log --oneline` | View commit history |

## Submission
- 📸 Screenshot of the repository folder (showing `index.html`, `style.css` and the hidden `.git` folder)
- 📸 Screenshot of the terminal with `git log --oneline` showing the three commits
