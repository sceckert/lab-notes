# Week 9 Lab
11/12/14

## Git and Github

Recall: 
- The problem of duplicate versions:
	- the single document model
	- the GoogleDocs version
		- works best at that point in time
		- asynchronicity is a problem 

Theoretical framework for version-control:
- model: Git
	- emerges from software engineering 
- The theory behind git:
	- reading, writing, and JOURNALING
	- Git = journal, a leger of what you've done
	-  When you're working in your computer, you're always in a directory and this directory is a vector
	-  Everytime you do something it changes the file 
		-  file system [] ----*-*-*-*-*-*----> (time)
		-  If don't save a different version, you lose this history
	-  To solve this problem:
		- add two more layers: the journal (git) and staging
		- file system [] ----*-*-*-*-*-*----> 
		- stage [] -------v1----v2----v3----------> 
		- journal[] ------v1----v2-----v3-------> 
	- We create a thing that brings together all of the changes, you package the changes on the stage in bundles -- then you put them in the journal with annotations (eg. as V1).  You continue doing this, creating official "restore" points, official versions. It also keeps track of what you've done for the day. 
	- staging is a temporary way to package changes
	- NB: this need not be digital. You could do this on your desk 
	- This allows you to show a timeline of your labor
	
### Git commands
- `git init` is what allows you to add things to the file system
- `git add` is what allows you to add files to the staging layer
- `git commit` is what allows you to add to git (journal)
- All of these above 3 steps are LOCAL 
- Next layer: remote server	
- `git push` takes a version on your local server and synchronizes it with a remote server -> Github (this is the free host for git)
- `git pull` takes a version on the remote server and pulls it to your local system
- remote server -----v1---v2---v3--->

Remote server
- the remote server allows you to have a universal timeline
- you have multiple people working on mutiple files, yet you both have a central, common timeline for versions
- If you try to synch with a remote branch that is different with yours, you have to synch up with it and then you can push your changes: error "Your head is behind"


### Using Git
- Make a directory
- Move into that directory
- Run `git init` to initialize versioning in that directory
- `ls -a` shows the hidden files that have been created
- `git status` will tell you what is happening in that directory and where you are
- create a file, test1.txt
- Now, run `git status`; it will tell you that there is one untracked file
- Run `git add`
- Run `git status` and we will see that that it has been staged
- Create another two files, stage the third
- Now, run 
- `git comit -m` - the m flag says put notes in line with command
- ```git commit -m "Today I added test and test3 to my repo"```
- What happens if you change a file after you change it?
- You have to stage it again (the earlier verion of test2 is still there) in order to have a later version.

### To push to Github:
- create a new repository
- `git remote add origin https://github.com/sceckert/code-poetry-test.git` adds the commit to the remote server
- For the first push to the server: 
`git push -u origin master`
- if you accidently put everything under version control ` rm -rf /git.`
- make more changes to test2, stage them, then 
- `git comit -m "my changes to test2"`
- `git push`
- Now, say you made a change to test 2 that you did not like
- `git checkout test2.txt` will rollback to the last staged version
- When github compares versions, it is a line-by-line comparison. For this reason must be plain text

Other uses:
- You can run a diff on the changes
- The work of editing; journals etc. can be done.

Our lab notes are due as a Github repository




