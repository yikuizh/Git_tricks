## Git_tricks



# Connect remote git repo to local directory (for JSC gitlab and github)

```bash
ssh-keygen -t ed25519 -C "YOUR EMAIL" # generate ssh key for GITHUB -- the key is under .ssh directory

```

```bash
cd existing_repo
git init # for GITHUB
git remote add origin https://icg4geo.icg.kfa-juelich.de/yzhang/git_tricks.git
git branch -M main
git push -uf origin main
git pull origin branch name # pull updates from remote
```
# For sychronize any changes from local to remote:
```bash
git status # visualize the changes you have made
git add `any changes you have made`
git commit 
git commit -a -m 'MESSAGE' # for github, you should always pass the message when commit; never empty message
git push -f origin main # (any branch you want)
git remote -v # check if you have the right remote link
```

# Create a new branch and go to it on any type of previous commitment:
```bash
git checkout -b test-master # create a new branch
git cherry-pick 33b58ffa5d155263af7e8c9933bd2175d3505317 # connect to any old version of commitment
git checkout `name` (switch to any branch or tag)
git branch -a # list all the branches you have

# then go and change the conflicts part 
# optional
git add xxxx
git cherry-pick --continue
update scripts


```
**Note: clone can basically pull down all branches in a repo in one time from remote; 
when switch branch or tag, you need to stay/do it at each of the directory where you cloned the repo**; 
when switch from `detached version` and you have changed something, first is to `stash` or `restore` the modified file and then `git checkout `branch
