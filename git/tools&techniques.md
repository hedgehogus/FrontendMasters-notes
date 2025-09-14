## search through logs
```git log --grep foo```  
--grep - search for target word

```git log --grep foo -p```  - also puts changes

## searching with filename
```git log -p -- file1 file2 ...```   

## BISECT
1. start git bisect ``git bisect start``
2. set the known bad commit ```git bisect bad```, uses the current one
3. set the known good commit ```git bisect good <commit>```  use ```git log --oneline```
4. test
5. ```git bisect <good | bad>``` depending on how the test runs
6. goto 4 until git tells you the commit

## Git bisect - Automated
Same setup with start, good, bad    
```git bisect run <cmd>```   
example: 
```git bisect run ./node_modules/.bin/vitest --run```

## reset after bisect
```git bisect reset```

## revert
```git revert <commitish>```   
```git revert <sha>```
- creates a new commit with revert changes (inverse commit)
