## add remote
``` git remote add <name> <uri>```     
``` git remote add origin ../hello-git```

## check remote
``` git remote -v``` - list out your remotes and their locations

## fetch
`` git fetch`` - does not merge changes to local

## see all branches from git fetch
`` git branch -a`` - git branch all

## pull 
fetches the changes and then merges those changes into your branch   
``` git pull <remote> <branch>```

## errors while git pull
```git branch --set-upstream-to=origin/master master```

## always rebase during pull
``` git config --add --global pull.rebase true```   
or    
``` git pull --rebase``` - each time
# push
```git push```
- fetch and merge for them
