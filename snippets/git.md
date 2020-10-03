# Git snippets
#### Replace the master branch with another one
This snippet will replace all the contents of the master branch with the ones from another.
This can be done by using the "ours" merge strategy, which, as stated on the wiki:
``` 
This resolves any number of heads, but the resulting tree of the merge is always that of the current branch head, effectively ignoring all changes from all other branches. It is meant to be used to supersede old development history of side branches. Note that this is different from the -Xours option to the recursive merge strategy.
``` 
``` 
git checkout otherbranch
git merge -s ours master
git checkout master
git merge otherbranch
```
You can later remove `otherbranch`. 

source: [Stack Overflow](https://stackoverflow.com/questions/2862590/how-to-replace-master-branch-in-git-entirely-from-another-branch)
