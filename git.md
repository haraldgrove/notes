---
title: git
created: '2022-03-03T03:59:16.384Z'
modified: '2022-03-03T04:01:25.391Z'
---

# git

First time setup
git config --global user.name "haraldgrove"
git config --global user.email haraldgrove@gmail.com
git config --global core.editor vim
git config --global color.ui true

SSH key setup
Checking for existing SSH keys
$ ls -al ~/.ssh
# filenames of supported public keys for GitHub are one of the following.
id_rsa.pub
id_ecdsa.pub
id_ed25519.pub
Generating a new SSH key
$ ssh-keygen -t ed25519 -C "haraldgrove@gmail.com"
Adding your SSH key to the ssh-agent
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519

Adding a new SSH key to your GitHub account
$ cat ~/.ssh/id_ed25519.pub
# Copy the contents of the file and paste it into the section for “new SSH key” on GitHub.

BRANCHING

https://www.atlassian.com/git/tutorials/using-branches


