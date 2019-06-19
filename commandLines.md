How to clone all branches and tags between remote git repositories
========================================================================

1. clone your old repo and cd into it
```
git clone https://yourOldRepo.git
cd yourOldRepo
```
2. list all the branches
```
git branch -a
```
3. fetch all of the remote branches and tags
```
git fetch origin
```
4. make sure all branches are checking out in your locally (use sh script to checkout)
```
git checkout -b xxx origin/xxx
```
5. add to your new remote
```
git remote add origin https://yourNewRepo.git
```
6. view existing remotes
```
git remote -v
```
7. push branches up to the new host
```
git push -u --all origin
```
8. make sure cover your new master branch success
```
git push --force origin master
```
9. push tags up to the new host
```
git push --tags
```

# Q&A:

## If use `for remote in `git branch -r | grep -v '\->'`; do git branch --track $remote; done` command line to set all your branches locally, the file tree structure of push result is:
					origin
						HEAD
						master
						origin
							migrate-branch1
							migrate-branch2
							migrate-branch3


## If only use `git push -u --all` command line to push your branch, you will find, sometimes you can not use old the branch cover to your new. Then must add an another option in the command line `--force`

