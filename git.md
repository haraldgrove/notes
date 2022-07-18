# git

## First time setup

```bash
git config --global user.name "haraldgrove"
git config --global user.email haraldgrove@gmail.com
git config --global core.editor vim
git config --global color.ui true
```

## SSH key setup

Checking for existing SSH keys
```bash
ls -al ~/.ssh
```
Filenames of supported public keys for GitHub are one of the following.
* id_rsa.pub
* id_ecdsa.pub
* id_ed25519.pub

Generating a new SSH key
```bash
ssh-keygen -t ed25519 -C "haraldgrove@gmail.com"
```

Adding your SSH key to the ssh-agent
```bash
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519
```

Adding a new SSH key to your GitHub account
```bash
$ cat ~/.ssh/id_ed25519.pub
```
Copy the contents of the file and paste it into the section for “new SSH key” on GitHub.

## BRANCHING

https://www.atlassian.com/git/tutorials/using-branches

List all available branches in the repository
```bash
git branch
```

Creating a new branch (does not check it out, i.e. focus is still on current branch)
```bash
git branch <branch name>
```

Switch to the new branch (with option -b, also create the branch)
```bash
git checkout <branch name>
git checkout -b <branch name>
```

Update the remote repository
```bash
git push --set-upstream origin <branch name>
```

Merge branch into main
```bash
git checkout main
git merge <branch name>
```

Merge main into branch
```bash
git checkout <branch name>
git merge origin/main
```

Delete a branch

```bash
git checkout main
git branch -d <branch name>
git push origin --delete <branch name>
```
