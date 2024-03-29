# basics of git

## make an repository
- there are two ways to make an repository
	1. `git init`
	2. `git clone`

## talk something about status

### basic commands
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
	git rm --cached README
	git rm README
	```
- use an example to show the simple commands
	1. create a file README in the current repository
	2. `git stasus`: shows README is untracked
	3. `git add README`: add readme to files to be tracked or committed
	4. modify README, use `git status`: shows the modified README
	5. use `git add README` *again*: add README to tracked files
		- `git rm --cached README`: not track README, file is now in the folder, not deleted
	6. `git commit -m "modify README"`: README now is unmodified
		- `git rm README`: README is now deleted and not tracked. no README file in the folder.


- dig deeper
	1.  `git status -s`: brief status of current repository.
		- M(red): modified not stateged
		- M(green): modifed stated
		- ??: untracked
		- A: new added to tracked files
	2. .gitignore file
		- the file can make files not tracked by git
		```
		- *.[ao]  #files end with a or o
		- *~ #files end with '~'
		- /debug #debug folder (recrusive)
		- /release/bin/ #only the bin folder
		- !my.o #track my.o file
		- doc/*.txt #ignore doc/notes.txt, but not doc/server/arch.txt
		- doc/**/*.pdf #ignore all .pdf files in the doc/ directory
		```
	3. show changes in detail
		- `git diff`: show the unstaged changes
		- `git diff --staged`: show the staged changes
	4. `git commit -a`: equals to git add and git commit. the unstaged files would not be in the commit list
	5. `git mv README.md README`: equals to the following
		```
		mv README.md README
		git rm README.md
		git add README
		```

- logs
	- logs are important when you want to check whether the logs 
	- `git log`: basic useage, shows commit logs
	- `git log -p -2`: shows difference of the most recent two commites
	- `git log --pretty=oneline`
	- `git log --pretty=oneline --graph`
	- `git log --since=2.weeks` : commits of recent two weeks, `--since, --after`, `--until, --before`
	- `git log -Sfunction_name` : list commits about the funciton, *-S is useful*
	- `git log --author=barney`

	
- amend
	- this would add the 
	```
	$ git commit -m 'initial commit'
	$ git add forgotten_file
	$ git commit --amend
	```

- unstage the changes
	- `git reset HEAD xxx.md`:this would unstage the chages, but the file is not changed

- cancel the unstaged changed
	- `git checkout file`: the staged files would not be changed, the unstaged would be changed.

## retmote
	- commands are easy, normally only four would be used often
	```
	git clone xxx
	git fetch
	git pull
	git push
	```
	- skill

## git tag
	- `git tag -a v1.4 -m "my version 1.4"` : this is a detailed tag
	- `git tag v1.5-lw` : this defines a light weight tag
	- `git show v1.4` : show detail info of tag v1.4
	- `git tag -d v1.4` : delete tag



## alias
	- alias is important. it can help you git easily
	`
		git config --global alias.co checkout
		git config --global alias.br branch
		git config --global alias.ci commit
		git config --global alias.st status
		git config --global alias.unstage 'reset HEAD --'
	`