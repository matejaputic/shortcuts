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

## Windows

`Ctrl + w{h,j,k,l}` move focus to {left, lower, upper, right} split

`Ctrl + w=` Equalize split
