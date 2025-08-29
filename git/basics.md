## create a repo
```git init```

## delete repo
once the git folder has been deleted, the repo does not exist

## add files to the index (staging area)
``` git add <path-to-file | pattern>```

## commit staged files
```git commit -m '<message>'```

## git status
```git status``` - will describe the state of your git repo which include tracked, staged and untracked changes

**SHA - Secure hashing algoritm**

## view history
```git log```

```git log --graph --decorate'''git log --graph --decorate

## inspect files
``git cat-file -p <some-sha>``
this will echo out the contents of the sha. This can be a commit, a tree or a blob 
