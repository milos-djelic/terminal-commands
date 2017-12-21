# Terminal commands 

## git
### Force remove all local branches except enumerated ones 
```git branch | grep -v 'master\|develop' | xargs git brach -df```

This line executes 3 commands: 
- `git branch` returns the list of all branches, one name per line
- `grep -v 'master\|develop'` returns all branch names that are neither `master` nor `develop` (one name per line); `-v` flag is for inverse selection;
- `xargs` performs the following command `git branch -df` for every branch name given in a list before (where names are separated with new lines); the flag `-d` is for branch deletion (short from `--delete`), where is `-f` to force the command execution (`--force`)


## docker
### Run an image locally with exposed port, environment variables and interactive bash
```docker run -i -t -p 8000:8000 -e APP_CONFIG='development' 384720 /bin/bash```

This command runs an image with the `IMAGE ID` starting with `384720`. If the command (or list of commands are added at the end of this line, Dockerfile is not run, but instead listed commadns (here, it's only one: `/bin/bash`).

Flags used: 
- `-i, --interactive` keeps STDIN open even if not attached   
- `-t, --tty` allocates a pseudo-TTY, which prints the file name of the terminal connected to standard input
- `-p, --publish list` publishs a container's port(s) to the host (if only one is given, (for example `-p 8000`) it exposes    docker port `8000` throught the same `8000` port
- `-e, --env list` sets environment variables. Example: `-e API_CONFIG='development'`
