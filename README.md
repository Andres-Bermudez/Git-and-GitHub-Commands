# Git and GitHub Commands

## Indice

- [Configure your identity in git](#1-configure-your-identity-in-git)
- [Basic Commands](#2-basic-commands)
- [SSH Key](#3-create-ssh-key)

## 1. Configure your identity in git:
    git config --global user.name "Your name"
    git config --global user.email "youremail@example.com"

## 2. Basic Commands:

### a. View global settings:
    git config --global -l

### b. Initialize a new repository:
    git init

### c. Add changes to a repository:
    git add .       // Add all files
    git add fileName        // Add specific file

### d. Confirm changes:
    git commit -m "Your message"

### e. Push changes to a GitHub repository:
    git push origin main

### f. Clone a repository:
    git clone https://github.com/user/repository.git

### g. View the status of a repository:
    git status

### h. Update your local repository with changes from the remote repository:
    git pull origin main

### i. View change history:
    git log

## 3. CREATE SSH key
### a. Generate a new SSH key:
    ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"   

### b. Add the SSH key to your SSH agent:
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519

### c. Copy your public ssh key:
    cat ~/.ssh/id_ed25519.pub

Go to GitHub, in Settings > SSH and GPG keys, and add a new SSH key, pasting the copied key.

You can now clone and push to repositories using SSH, without needing to enter your credentials.

### d. Make sure the repository URL is configured to use SSH and not HTTPS:
    git remote -v
This will display the URL of the remote origin. It should look something like:

    origin  git@github.com:user/repository.git (fetch)
    origin  git@github.com:user/repository.git (push)

If you see a URL that starts with https://, you'll need to change it to the SSH version:

    git remote set-url origin git@github.com:user/repository.git

### e. Verify SSH Agent Configuration:
    eval "$(ssh-agent -s)"      // Start the SSH agent
    ssh-add ~/.ssh/id_ed25519       // Add your SSH key to the agent

### f. Test SSH Connection to GitHub:
    ssh -T git@github.com


