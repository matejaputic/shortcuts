# Git

`git checkout -b myfeature develop` Branch off from `develop` branch, switch to branch `myfeature`

Merge work from `myfeature` into `develop` branch
```
git checkout develop
git merge --no-ff myfeature
git branch -d myfeature
git push origin develop
```

`git add -A` stage all changes

`git add -u` stage modifications and deletions, without new files

`GIT_SSH_COMMAND="ssh -i ~/.ssh/id_rsa_example" <git command>` Specify identity file

# Tmux

`ls` List active sessions

`a -t n -d` Attach to session number `n` and disconnect any other screens

# Vim

## Moving

`zz` Center current line on screen

`Ctrl + e` Move screen up without moving cursor

`Ctrl + y` Move screen down without moving cursor

## Windows

`Ctrl + w{h,j,k,l}` move focus to {left, lower, upper, right} split

`:vsplit <another file>` Open another file in side-by-side split

`Ctrl + w=` Equalize split

`Ctrl + wo` Close other windows

## Bookmarks

`ma` Set position for mark `a`

`` `a`` Jump to location at mark `a`

# Conda

`conda info --envs` View a list of environments

`conda create --name myclone --clone myenv` Clone an environment

`conda remove --name myenv --all` Remove an environment

`conda list --explicit > spec-file.txt` List packages installed in environment, write to `spec-file.txt`

`conda create --name myenv --file spec-file.txt` Create new environment from `spec-file.txt`

# System

## GPU

`fuser -v /dev/nvidia*` What process(es) are using the GPU?

## Rsync

`rsync -avzP –include ‘*.txt’ –exclude ‘*’ /src/dir testuser@10.10.1.10:/dst/dir` Sync a local directory to a remote directory, with progress bar

`rsync -e "ssh-i ~/.ssh/abc_rsa" /src/dir testuser@10.10.1.10:/dst/dir`

More at: https://linuxtechlab.com/start-with-rsync-command-8-rsync-examples/

## SCP

`scp -i ~/.ssh/abc_rsa` Use identity file `abc_rsa`
