# basics of git

## make an repository
- there are two ways to make an repository
	1. `git init`
	2. `git clone`

## status
- there are several status of a file
	1. untracked
	2. unmodified
	3. modified
	4. staged
- simple commands
	```
	git add README
	git status
	git commit -m "first commit"
	```
- use an example to show the commands
	1. create a file README in the current repository
	2. `git stasus`: shows README is untracked
	3. `git add README`: add readme to files to be tracked or committed
	4. modify README, use `git status`: shows the modified README
	5. use `git add README` *again*: add README to tracked files
	6. `git commit -m "modify README"`: README now is unmodified
- commands deeper
	1. `git status -s`: brief status of current repository.
		- M: modified
		- MM:

