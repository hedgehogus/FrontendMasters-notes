## stash
```git stash -m``` will take every change tracked by git (change to index + change to work tree) and store that result, much like a commit, into the 'stash'     
us git stash when you want to record the current state of the working directory and the index, but want to go back to clean working directory. 
The command saves your local modifications away and reverts the working directory to match the HEAD commit.   

shashes can be listed out:   
``` git stash list
git stash show //more readable
git stash show [--index <index>]```
   
## to pop the latest stash
``` git stash pop```
``` git stash pop --index 1```

`` git reset --soft HEAD~1`` - return commited change
