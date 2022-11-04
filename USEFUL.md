# List of useful commands

## Package managers

### Clearing cache

#### Npm

* npm cache clean –force

#### Yarn

* Use `yarn cache clean` to remove all the cache
* If you want to remove a specific lib's cache run `yarn cache dir` to get the right yarn cache directory path for your OS, then `cd` to that directory and remove the folder with the name + version of the lib you want to cleanup.
* Use `yarn set version berry` to switch to latest version (make sure to be in ~/ folder)
* Use `yarn set version classic` to switch to v1 version (make sure to be in ~/ folder)

## Git

### Stashing changes for later
```zsh
# save changes to stash
git stash
# apply changes from stash
git stash apply
# delete old stash
git stash drop
# apply stash and delete it
git stash pop
```

### Disable/enable file tracking
```zsh
# disable tracking of file changes
git update-index --assume-unchanged path/to/myfile.ext
# enable file changes tracking
git update-index --no-assume-unchanged path/to/myfile.ext
```

### Reset last commit but leave changes stashed
```zsh
git reset --soft HEAD~ 
```

### Ammend last commit
```zsh
git commit --amend --no-edit
```

### Change someone else's PR
```
git remote add TheirName git@github.com:TheirName/reponame.git
gh pr checkout 1234 # or gh pr checkout https://github.com/main-org/repo/pull/1234
git push git@github.com:TheirName/reponame.git <branch-name>:<branch-name>
```

## Browser

### Show Shadow DOM in Mozilla
Go to advanced settings via `about:config` and set 
```
devtools.inspector.showUserAgentShadowRoots: true
devtools.inspector.showAllAnonymousContent: true
```

### Show Shadow DOM in Chrome
Go to dev tools settings and under `Elements` check `Show user agent shadow DOM`

## Terminal

### Kill process running on port `1234`

```zsh
sudo lsof -i tcp:1234
# Returns👇 where PID is the ID of our process
# COMMAND  PID USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
# node    5261 miro   23u  IPv4 0x15e7fe15968959d9      0t0  TCP *:http-alt (LISTEN)

# Next we kill the process with that ID
kill -9 5261
```

Or in single line:
```zsh
sudo kill `sudo lsof -t -i:1234`
```

## Vim
* Save file: `:w`
* Quit: `:q`

## Docker
* Download image: `docker pull imagename`
* Run container: `docker run --name containername imagename`
* List all images: `docker ps`
* List all containers: `docker container ls -a`
* Remove container: `docker container rm 123124`
* SSH to container: `docker exec -it containername /bin/bash`

### Setup ubuntu machine with nodejs
1. `apt-get update`
2. `apt-get curl`
3. `apt-get curl -sL https://deb.nodesource.com/setup_14.x | bash` (change number for the version)
4. `apt-get install -y nodejs`

## Windows
* Create empty file: `fsutil file createnew emptyfile.txt 0`
