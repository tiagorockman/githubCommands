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
<ul>
What This Does 
<li>Initializes a local Git repository</li>  
 <li>Stages the project files </li>  
  <li> Creates the first commit </li>  
   <li>  Renames the default branch to main </li>  
   <li>  Creates a new public GitHub repository named ReleaseManager </li>  
  <li>   Adds the GitHub repository as origin </li>  
  <li>   Pushes the local code to GitHub</li>  
   <li>  Create a Private Repository Instead</li>  
</ul>
If you want the repository to be private, use:

```powershell
gh repo create ReleaseManager --private --source . --remote origin --push
```

### In case of --remote origin fails
* If GitHub created the repository but the remote was not added locally, you can fix it manually:
```powershell
git remote add origin https://github.com/tiagorockman/ReleaseManager.git
git branch -M main
git push -u origin main
```

* If origin already exists
```powershell
git remote -v
```

* If origin is wrong, update it:
```powershell
git remote set-url origin https://github.com/tiagorockman/ReleaseManager.git
```
Then

```powershell
git push -u origin main
```

```powershell
* git remote -v
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

