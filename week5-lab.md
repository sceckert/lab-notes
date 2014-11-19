# Week 5 Lab
10/8/2014

## Files and file permissions; wget and brew

## Key Commands
### Friends!
```head
tail
cat
man
```

### Search
``` locate
find
grep
awk
```

### Network
```wget
curl
ssh
ping
traceroute
```

### Flow [allow you to string commands together]
```|
>>
xargs
```


### Today: What is brew?
Question: How does package control and installation work?
- When you install an application (more than just a file), the program installs itself in many different places. There are many dependancies and using pieces of the operating system located elsewhere. 
- Each program doesn’t have to reinvent the wheel
- A problem: what happens when you have two programs that are both using a package but different versions (they’re both dependent on the same library).
	- Microsoft Windows: there are “dll” (shared components of applications) library it will install and select dll libraries.
	- Linux/Unix: all the programs are checked into a secure repository (rather than going to the internet and downloading) that keeps and checks into all the possible files and applications for that flavor of linux (Ubuntu, Debian, FreeBSD). 
		- This guarantees the stability of the system: it’s difficult for a developer to get into that repository, but Unix will take care of the dependency conflicts and security problems.
		- for Debian, this is called “aptitude” (we’ll be using this when we’re on a remote server)
	- Mac: the Mac ecosystem does not provide an official repository. However, Homebrew creates a secure unofficial one. 
	- There are other repositories that are connected to languages:
		- Ruby’s repository is called “gem”
			- you call “gem install [program]”
		- Python’s is “pep” 
			- you call “pep install [program]”

To run wget
- Navigate into the folder that you want the file saved in
- `wget [url]`

nb: you can use curl for a similar thing, but it’s more cumbersome

### Files and extensions

- To see the first few lines of a file: 
`head [document]`

- To see the last few lines of a file
`tail [document]`

- To open a file: `open [file]`
- Applications read extensions. 
	- When you open a file with .pdf the system will go through and find out how to open that extension
	- The PDF reader understands it.
	- If we rename that file, `cp heidegger.pdf random.name`
and open it using `head`, we will seen it is the same file
	- However, if we try to open the file, the system doesn’t recognize the extension.
	- Likewise, if we create a file with “.pdf” extension with some random text `echo "some stuff" > testingpdf.pdf`
	- We can open this file using head
	- But if we try and open it, we get an error. This is because it is missing the proprietary Adobe encoding.

KEY: The file is the file; you can name it what you want (though other things will try to guess what it is by the extension)

### Search

- To find files:
`locate`
- The `locate` command looks at the database of files that sits in your system; a super-fast search
- Like Spotlight, it is indexed (weekly, though you can change this)
- `locate` uses regular expressions
		- `locate “test*”`
- `locate `` —regex test*`

### Additional commands:
- To recursively remove with confirmation: `rm -ri test*`
- shortcut: `rmdir` — BUT THIS DOES not take the confirmation command	

