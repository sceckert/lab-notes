# Week 6 Lab
10/15/2014

## Using |, grep, wc


UNIX early on split into two different families: 
- Linux
- FreeBSD

Make directory, test files  
Using the `find` command
- `find . -name "oran*"` This will find things in the directory only the files beginning with "oran"  
- `find . -name "*.md"` This will find only files with .md.
- If you only want to search home directory 
`find ~ -name "*.txt"`  - this will search the home directory and find all things with .txt extension


Using `grep`
- grep [what] [where]
- `grep` is command that prints patterns on the screen.
- `grep "Moby Dick" pg2701.txt`
- `grep "orange" oranges.txt` will search oranges.txt for "orange
- `grep "orange" *` will search in that directory
- If `grep` encounters a directory, it will need a recursive command:
`grep -r "orange" *`

Using `wc`
- Definition: wc --word, line, character, and byte count

To count the number of times "whale" is used in Moby Dick", use `grep` and pipe to `wc`
- `grep "whale" pg2701.txt  | wc`


To count the number of times "oranges" is used in oranges: `grep "orange" oranges.txt | wc`
- We get an output: `       5       9      62`
- 5 lines, 9 words total used in these lines, 62 bytes (characters)
- If we add another word to one of the lines, `wc` will print:`       5       10      62`

To search for instances of "ls" has been used in history:
`history | grep "ls"`

To sort oranges.txt:
`sort oranges.txt` [nb: this does not change the integrity of the file or reorder the lines, it merely re-orders what prints]

To search for unique occurences of words on unique line:
- `sort oranges.txt | uniq -c`
- It will print: 
```1 apple meh
   3 banana
   1 mushroom
   1 orang orange
   1 orange
   1 orange 
   1 orange are excellent 
   1 oranges are great
   1 peach
```

- without `-c`, it will print without the counts


*KEY: the idea of the word, the character, and the sentence are built into the shell => the fact that we can do lexical analysis from the command line shows us that the Unix system has a deep-seated sense of linquistics*  
NB: there is some further level where this is all Os and 1s, but the operating system itself is a layer above this. Each encoding at this level can be expressed in configuraitons of 1s and 0s. [read in *D is for Digital*]

To use `sed`
- "substitute" something into something"
- create a text file with lines of day and night
- `sed 's/day/night/' 24hr.txt`
- all of the lines of "day" will appear as night"
- NB: this only changed in the output
- To substitute IN THE FILE, add an extra `''` and `-i` flag: `sed -i '' 's/day/night/' 24hr.txt`
- THIS IS A DANGEROUS Command
	- better: print this into a new file called "night.txt" `sed 's/night/day/' 24hr.txt >> night.txt`

You can string scripts together to create programs to execute multi-line scripts
Example:
-replace every line "Moby Dick" with "pumpkin" and pump it into a new file:
`sed 's/whale/pumpkin/g' pg2701.txt >> mobydick.txt`
- the `g` makes this a global command, rather than just the first instance in the line

## Assignments
### Assignment 1
- First, analyze the treatment of gender in *Moby Dick*
- Create a new project directory
- Grab the text of *Moby Dick* and put in this directory
- Make a file, male.txt, with a list of male-gendered words, eg "he", "male", "men"
- Make another file, female.txt, with list of female-gendered words, eg "female", woman";
- We are going to grep the context (the words that are near) of all the female words and grep the context of all the male-gendered words and put those into separate files. 
- Eliminate the stopwords (the, a, it, etc)
- Sort them

### Assignment 2
Weasel Words: take a piece of writing that you wrote and check with clarity 
- create directory
- copy 3 papers that you wrote into this directory
- make these files plain text
- make a list of 3 "weasel words": words that you hate in writing, words that good writers shouldn't be using
- write a script that replaces these weasel words with something, e.g. a space, etc.

Tip: If you look at the `grep` manual, you will see that it can take a file as an attribute (so one could use the female.txt or male.txt)
- `grep -f` will obtain patterns from a file. 