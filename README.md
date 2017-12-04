# Terminal commands 

## git
### Force remove all local branches except enumerated ones 
```git branch | grep -v 'master\|develop' | xargs git brach -df```

This line executes 3 commands: 
- `git branch` returns the list of all branches, one name per line
- `grep -v 'master\|develop'` returns all branch names that are neither master nor develop (one name per line); `-v` flag is for inverse selection
- `xargs` performs the following command `git branch -df` for every branch name given in a list before (where names are separated with new lines); the flag `-d` is for branch deletion (short from `--delete`), where is `-f`to force the command execution (`--force`)
