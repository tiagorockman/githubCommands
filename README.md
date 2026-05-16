# GITHUB COMMAND

## Create the Repository from the Command Line

If this project is not on GitHub yet, you can create the remote repository without using the GitHub website by using the GitHub CLI (`gh`).

### Prerequisites

Make sure these tools are installed:

- `git`
- `gh` (GitHub CLI)

You can check them with:

```powershell
git --version
gh --version
```

### Authenticate with GitHub
```powershell
gh auth login
```

### Create and Publish the Repository
```powershell
cd c:\Users\tiago\Documents\Projetos\ReleaseManager
git init
git add .
git commit -m "Initial commit"
git branch -M main
gh repo create ReleaseManager --public --source . --remote origin --push
```

What This Does
  Initializes a local Git repository
  Stages the project files
  Creates the first commit
  Renames the default branch to main
  Creates a new public GitHub repository named ReleaseManager
  Adds the GitHub repository as origin
  Pushes the local code to GitHub
  Create a Private Repository Instead
  If you want the repository to be private, use:
```powershell
gh repo create ReleaseManager --private --source . --remote origin --push
```

### Optional Git Identity Setup
If Git asks for your identity before committing, configure it with:
```powershell
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### Safety Tip
Before running git add ., review the files that will be included:
```powershell
git status
```

Make sure no secrets, local artifacts, certificates, or generated files are being committed.

