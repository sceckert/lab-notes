## Week 1: Lab
Lab: 1 Wed. 9/10/14

// how media scholars come to understand the tools.
// what technical environment are you working in ---> how do you take ownership


### The Terminal:
Why the terminal?
- In 1970s the larger computer was a huge machine with a little terminal that users would use to log into the computer, do their work, and log out. Shared computing experience. Many computers nowadays don't have terminals.
- In contemporary computing, our machines now have usually one user (though "accounts" are an artifact) 
- Cloud services now are bringing us back to the earlier shared computing experience w/ Dropbox, Facebook, etc.
- this is not a terminal, but a terminal "emulator" that emulates earlier one
- terminal is a text prompt
there are commands that we can use in the terminal:
- the way we communicate with the terminal is in "bash"
- there is a family of computers from the 1970s called "Unix" (there are many derivatives, freeBSD, etc)
     - Unix = a particular way of interfacing computers
     - Unix is everywhere; it is a philosophy of using computers and it has found its way into all the computers we use today (Mac, Android, etc). 
     - Unix is long lasting
          - Response to users who push back against the terminal: this way of computing is incredibly stable. It's been in development for a long time and will continue to be around. 
           - Tips for looking at tools: Will is be around for a long time? Will Word, Evernote be around in 20 years so that you'll be able to access your notes? Will you be able to modify it? Is the sourcecode free and open? Does it allow you to modify? Is it proprietary? Does the program store its information in proprietary format or in plaintext? Will it grow with you?
     - Unix is human-friendly: the idea of readability is embedded into the Unix philosophy; at a base level the system the idea of plaintext is in the philosophy --> this idea of "human readable" text (not binary) that drives the philosophy ** KEY **
     - Unix interface is standard; everything works the same across every interface (as compared to individual applications that each have their own metaphors for the UI system - eg Word, Photoshop, InDesign)

### Common commands
- Tools to orient you in the folder structure
pwd: path to working directory
ls: list
// by default, Macs set working directory as your home
// if you type ls and nothing happens, you might be in an empty
man: manual (the help --- type "man [insert command here]" and it will give you defn)
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


### Search Tools
find
grep
said
awk

// for windows users using Seguin, Seguin is a sandbox, but it does not have access to things outside its own directory. You have to transfer things.
// there is a system that advises the directory structure, ie tells the system to install things into different directories. "bin" contains a simple language
cd ~: takes you home (this is an arbitrary path that you could change if you wanted to)
 // All Unix command have a syntax
     transitive verb > adverb >  object
// example:
ls /bin/
     = "list contents of the directory bin"
// in order to specify the object, give it a path; EVERYTHING IS A PATH
// there are some commands that require you to specify a location
mkdir [name of directory]: make directory 
cat: concatenate files and print on the standard output (note, one can change the standard output to something else, eg braille reading device)

// Unix is based on plaintext. Why is this good? Can you text search PDFs? If you store your archive in plaintext, they will be easy to store in a library. But if there is something in another format, eg PDF (only readable by Adobe), or Word .doc, that means that it is less portable and the format will not necessarily be preserved. Often this occurs with  proprietary. How will we view this in a century? How do you continue to organize?
// When files are in plaintext, it will be easy to mine this for information, vs. PDFs (Adobe only lets you search fulltext from within itself).  We want governments to release data in plaintext. When you try and search a proprietary document. The publisher will retypeset your document anyway.  

PRINT IS FLAT; CODE IS DEEP
- plaintext is easy to search move 

Note: when you're in your home directory, you usually have all privileges to the root, but if you move out, you lose permissions.



### LOG OF COMMANDS IN THE TERMINAL

Last login: Mon Sep  1 09:13:25 on console
dyn-160-39-227-198:~ Sierra$ ls
Applications               grandison
Calibre Library               hilt.png
Desktop                    ibt_application.log
Documents               ibtsa.log
Downloads               lifehack.html
Dropbox                    mallet
Google Drive               marc2bib.pl
Library                    numpy
Movies                    oasys.log
Music                    paperstack.html
Pictures               prism
Public                    programmingstuff
R2MALLET.r               records.marc
Sites                    src
demo.gephi               wordpress-exhibit-read-only
dyn-160-39-227-198:~ Sierra$ pwd
/Users/Sierra
dyn-160-39-227-198:~ Sierra$ ls
Applications               grandison
Calibre Library               hilt.png
Desktop                    ibt_application.log
Documents               ibtsa.log
Downloads               lifehack.html
Dropbox                    mallet
Google Drive               marc2bib.pl
Library                    numpy
Movies                    oasys.log
Music                    paperstack.html
Pictures               prism
Public                    programmingstuff
R2MALLET.r               records.marc
Sites                    src
demo.gephi               wordpress-exhibit-read-only
dyn-160-39-227-198:~ Sierra$ man ls
dyn-160-39-227-198:~ Sierra$ man man
dyn-160-39-227-198:~ Sierra$ cd ..
dyn-160-39-227-198:Users Sierra$ cd mallet
-bash: cd: mallet: No such file or directory
dyn-160-39-227-198:Users Sierra$ ls
Shared     Sierra
dyn-160-39-227-198:Users Sierra$ cd Sierra
dyn-160-39-227-198:~ Sierra$ ls
Applications               grandison
Calibre Library               hilt.png
Desktop                    ibt_application.log
Documents               ibtsa.log
Downloads               lifehack.html
Dropbox                    mallet
Google Drive               marc2bib.pl
Library                    numpy
Movies                    oasys.log
Music                    paperstack.html
Pictures               prism
Public                    programmingstuff
R2MALLET.r               records.marc
Sites                    src
demo.gephi               wordpress-exhibit-read-only
dyn-160-39-227-198:~ Sierra$ cd mallet
dyn-160-39-227-198:mallet Sierra$ cd ..
dyn-160-39-227-198:~ Sierra$ cd mallet
dyn-160-39-227-198:mallet Sierra$ cd -
/Users/Sierra
dyn-160-39-227-198:~ Sierra$ cd-
-bash: cd-: command not found
dyn-160-39-227-198:~ Sierra$ cd -
/Users/Sierra/mallet
dyn-160-39-227-198:mallet Sierra$ pushd mallet
-bash: pushd: mallet: No such file or directory
dyn-160-39-227-198:mallet Sierra$ cd ..
dyn-160-39-227-198:~ Sierra$ pushd mallet
~/mallet ~
dyn-160-39-227-198:mallet Sierra$ popd
~
dyn-160-39-227-198:~ Sierra$ ls
Applications               grandison
Calibre Library               hilt.png
Desktop                    ibt_application.log
Documents               ibtsa.log
Downloads               lifehack.html
Dropbox                    mallet
Google Drive               marc2bib.pl
Library                    numpy
Movies                    oasys.log
Music                    paperstack.html
Pictures               prism
Public                    programmingstuff
R2MALLET.r               records.marc
Sites                    src
demo.gephi               wordpress-exhibit-read-only
dyn-160-39-227-198:~ Sierra$ cd /
dyn-160-39-227-198:/ Sierra$ ls      