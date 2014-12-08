# Week 12 Lab

11/25/2014

## Git, Github

### Final Assignment:
- Take notes on cheat sheets
- Take one of the notes that we have to ourselves and make it a tutorial for someone else
- Write for Minimally Viable Digital citizen as your audience
	- this is the minimum 

Minimally Viable Digital Citizen
- Will be constituted by these tutorials
- Create a notion of citizenry
- 

### Recall
- The aim of this course has been to give us a degree of control over the underlying infrastructure
- In order to be a digital citizen, citizens need to make informed decisions about computers, networks, 


### What should a minimally viable citizen know:
- Markdown 
- Pandoc
- FS - file structure
- Terminal
	- Find
	- Sed
	- Grep
	- Moving and managing files
- Networking
	- Ping
	- Traceroute
- Cryptography
	- PGP
	- bitcoin 
- Central repositories
	- app, brew
- Git
- File permissions


### Git: Pull Requests
- You have a remote server and everyone can push and pull on the same remote server
- If you don't have an editing structure, there is only one person managing
- With branching, you have a primary remote server that has branches for each user 
- Branch: makes an exact copy of a repository on your account
- Inside that branch, you have full permissions
- Once you have editted or made changes on your branch, you file a pull request, `git pull`
- This alerts the admin of the main repository, who gets a `diff` summmary of the changes on a line-by-line basis.
- This conceptual model (modular tasks that can be easily integrated into the main task) is what enables peer-production
- Software companies all have models of version control (some based in git, some slightly more complicated).
- Can use "Split" to accept changes on a line-by-line basis

### File Permissions and Access
- In the history of modern computing: public computer
	- For early computers you had to sign up for a block on a computer
	- On that machine, there are multiple users
	- When you have multiple users, you have user management so as to manage access and preserve files
	- Centralized systems are easy to control, monitor
- Rise of the personal computer
	- Now, you write something on your own personal computer. 
	- Your machine is wholly your own, you monitor what is on it
	- To share files, you had to physically transfer files
	- Much higher privacy
	- Decentralized model
- Rise of the Internet and cloud computing
	- What is the cloud? A giant computer that belongs to a remote server owned by Google, Amazon, etc
	- Return to centralized computing! 
	- Much easier for Google, Amazon to control
	- Centralized allows for easier management, but you do give up privacy
	- Companies anticipate this. Now, Microsoft want you not to have a local install of Microsoftword, wants you to log into one remote server. 
		- Versions of software are taken care of by the company, updates, backup
		- BUT, information all controlled by that server
		
### File Permissions
- When you get a machine, the first thing that it asks you is to create a new user account
	- Users are baked into the computer 
- Example: you encounter a "Permission denied" message
- Recall: `ls` lists things
- `ls -l` shows the permissions related to the file, the date created
- Example: `drwxr-xr-x    15 Sierra  staff    510 Nov  1 13:44 test`
	- permissions		size		user		group		date		time		file
- Groups
	- What the group does is allow for users to have keys to files
	- By default in the system, your user is that group name
	- To show the groups: `id [username]` will list the groups this particular user is a part of
- Permissions
	- Directories are prefixed with `d`
	- Permissions are divided into three sections
	- `rwx|rwx|rwx`
	- (U)User	| (G) Group | (O) Other   
	- From this you read from left to right to determine who has permissions
	
### Changing permissions
- Say that you want to give your group write permissions to a file, test.txt
- Change file mode bits: `chmod g+w test.txt`
- The permissions for the file change from  `-rw-rw-r--     1 Sierra  staff      0 Nov 26 12:31 test.txt`
to `-rw-r--r--     1 Sierra  staff      0 Nov 26 12:31 test.txt`
- Hacking!!
	- You log into somewhere where you don't have permissions, then you elevate your permissions to system administrator with `sudo` permisssions
   - How? `sudo` is the superuser command that can do anything
   - Why are permissions are important? Because sensitive data is stored here 
- To modify things in user, you can modify anything
- To modify things on root, need sudo
- On the root: `sudo touch text.xt`
- This gives you the ability to read and write to the root.
- On the remote server, if you try to log in and make changes, you will receive permission denied messages
- To create a user, must find the default administrator, create a new user, and then remember to delete the administrator because this is a mode of attack.

### Pull Requests
- Can accept line-by-line
- The changes are made line-by-line