# Git

`git checkout -b myfeature develop` Branch off from `develop` branch, switch to branch `myfeature`

Merge work from `myfeature` into `develop` branch
```
git checkout develop
git merge --no-ff myfeature
git branch -d myfeature
git push origin develop
```

# Vim

## Moving

`zz` Center current line on screen

`Ctrl + e` Move screen up without moving cursor

`Ctrl + y` Move screen down without moving cursor

## Windows

`Ctrl + w{h,j,k,l}` move focus to {left, lower, upper, right} split

`Ctrl + w=` Equalize split

`Ctrl + wo` Close other windows

# Conda

`conda info --envs` View a list of environments

`conda create --name myclone --clone myenv` Clone an environment

`conda remove --name myenv --all` Remove an environment

