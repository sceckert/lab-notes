## Week 1: Lab
Lab: 1 Wed. 9/10/14

## Questions to keep in mind
- Should media scholars understand the tools that you're working with?
- What technical environment are you working in and how do you take ownership?


### The Terminal:
Why the terminal?
- In 1970s the larger computer was a huge machine with a little terminal that users would use to log into the computer, do their work, and log out. Shared computing experience. Many computers nowadays don't have terminals.
- In contemporary computing, our machines now have usually one user (though "accounts" are an artifact) 
- Cloud services now are bringing us back to the earlier shared computing experience w/ Dropbox, Facebook, etc.
- This is not a terminal, but a terminal "emulator" that emulates earlier one
- The terminal is a text prompt
- The language we communicate with the terminal with is called "bash"
- There is a family of computers from the 1970s called "Unix" (there are many derivatives, freeBSD, etc)
     - Unix = a particular way of interfacing computers
     - Unix is everywhere; it is a philosophy of using computers and it has found its way into all the computers we use today (Mac, Android, etc). 
     - Unix is long lasting
          - Response to users who push back against the terminal: this way of computing is incredibly stable. It's been in development for a long time and will continue to be around. 
           - Tips for looking at tools: Will is be around for a long time? Will Word, Evernote be around in 20 years so that you'll be able to access your notes? Will you be able to modify it? Is the sourcecode free and open? Does it allow you to modify? Is it proprietary? Does the program store its information in proprietary format or in plaintext? Will it grow with you?
     - Unix is human-friendly: the idea of readability is embedded into the Unix philosophy; at a base level the system the idea of plaintext is in the philosophy --> this idea of "human readable" text (not binary) that drives the philosophy ** KEY **
     - Unix interface is standard; everything works the same across every interface (as compared to individual applications that each have their own metaphors for the UI system - eg Word, Photoshop, InDesign)

### Common commands
- Tools to orient you in the folder structure

```
pwd: path to working directory
ls: list
clear: clears the screen
cd:  change directory
cd .. : one directory up
cd . : stay in this directory
. : this directory
.. : one directory up
... : two directories up
cd ../..:  change directories two up
cd - : goes to the last directory where you were
pusd [directory]: adds it to the stack of directories
popd: removes it from
cd /: goes to the root for your file system
cd ~: takes you home (this is an arbitrary path that you could change if you wanted to)
```
- By default, Macs sets your working directory as your home
- If you type `ls` and nothing happens, you might be in an empty
man: manual (the help --- type `man [insert command here]` and it will give you a definition)

### Search Tools
```find
grep
said
awk
```
### Notes
- For windows users using Seguin, Seguin is a sandbox, but it does not have access to things outside its own directory. You have to transfer things.
- There is a system that advises the directory structure, ie tells the system to install things into different directories. "bin" contains a simple language
- NB: when you're in your home directory, you usually have all privileges to the root, but if you move out, you lose permissions.

### Syntax:
- All Unix command have a syntax: transitive verb > adverb >  object
	- example:`ls /bin/` = "list contents of the directory bin"
	- In order to specify the object, give it a path; EVERY FILE IS A PATH
- There are some commands that require you to specify a location:
	- Example:  `mkdir [name of directory]`= make directory 
	- `cat [filename]` concatenate files and print on the standard output (note, one can change the standard output to something else, eg braille reading device)

- Unix is based on plaintext. 
	- Why is this good? 
	- Other file formats are not necessarily searchable; plaintext is.
		-  If you store your archive in plaintext, they will be easy to store in a library. 
		- If a file is in another format, eg PDF (only readable by Adobe), or Word .doc, that means that it is less portable and the format will not necessarily be preserved. Often this occurs with  proprietary. How will we view this in a century? How do you continue to organize?
	- When files are in plaintext, it will be easy to mine this for information, vs. PDFs (Adobe only lets you search fulltext from within itself).  We want governments to release data in plaintext. When you try and search a proprietary document. The publisher will retypeset your document anyway.  

### Takeaways: 
- PRINT IS FLAT; CODE IS DEEP
- Plaintext is easy to search move 




  