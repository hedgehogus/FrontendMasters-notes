## create a repo
```git init```

## delete repo
once the git folder has been deleted, the repo does not exist

## add files to the index (staging area)
``` git add <path-to-file | pattern>```
``` git add .```

## commit staged files
```git commit -m '<message>'```

## git status
```git status``` - will describe the state of your git repo which include tracked, staged and untracked changes

**SHA - Secure hashing algoritm**

## view history
```git log```

```git log --graph --decorate'''git log --graph --decorate```

## inspect files
``git cat-file -p <some-sha>``
this will echo out the contents of the sha. This can be a commit, a tree or a blob 

## create a branch
``git branch foo`` - create a branch
``git branch`` - shows a list of branches

## switching branches
```
git switch <branch name>
git checkout <branch name>
```
``git checkout -b merge-foo``

## merge branches
``git merge <branchname>

## log after merge 
``git log --oneline --graph --parents``

## rebase 
``` git rebase master```

## history of mowing through branches 
``` git reflog```
`` git reflog -3``` - 3 last logs
