# Week 10 Lab
11/19/2014
## More on Git, Github, Branching

### Recap:
Recall from last time: versioning allows you to fashion your versions on the universal timeline.

Branching:
- Recall Model 1: one remote server and many collaborators model
	- Each individual logs in and has permission to work in the directory on the remote server
	- conflicts: if two users attempt to edit the same thing, their clobber the other person’s changes
	- This is using Git but is more like Googledoc
-To solve this problem: Branching
	- Imagine this as syllabi, with C&P 2014. C&P 3015 would be a new branch
	- The branches diverge, but you CAN merge them 
	- Branching is an added level of versioning
		- Revisions are not versions; this is a way to treat different (i.e., a syllabus, a project
	- Developing
		- Branching is one way to have a testing branch. This can be merged with a live branch to make live
- Model 2: Branches
	- Rather than having individual all contributing to a single remote server directory, you branch the remote server
	- One branch will be designated the main branch
	- Users will push their changes to their branch, and their branches, when at a finished version is done, you file a pull request.
	- the administrator of the main branch then reviews the code in the pull request and can accept/deny
	- This is a great workflow for project management and for managing a journal. This is, in essence an editorial workflow.

### Assignment
- open a new repository called “lab-notes” and put lab notes under version control