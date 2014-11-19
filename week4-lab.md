# Week 4: Lab 
10/1/2014

## TERMINAL PRACTICAL COMMANDS
GPS
```
pwd
ls
tab everything
cd
echo
cat
less
clear
man
-h
—help
history
```

FILES
```
mkdir
touch
cp [DANGER]
mv [DANGER]
rm [DANGER]
```

OPERATIONS
```
> [DANGER]
>>
|
!
```

PATHS/SHORTCUTS
```
/ root
~ home
- previous
```

SEARCH
```
find
grep
awk
```

NETWORK
```
scp
ssh
ping
traceroute
rsync
wget
```

POSIX [the Unix syntax]
[verb] 		[adverb]		[noun]
```
rm  			-ri 			temp/
```
“command” 	“flag” 		“target”

### Best practices in file labeling: 
no spaces  
no capitals  
-i (or subject)
- NB: you can re-alias rm to not delete, but instead move into a trash directory (and then write into a script to empty that directory every week). 
- Get into the habit of naming files with extensions
- If you mean directory, put a “/“ at the end

Unix Philosophy:
- produce plain text
- by piping the output of one command into another, you can do more complicated things. 


## Testing Commands
- Make a directory called “temp”
` mkdir temp `
- Make a file:
```
touch test.txt
ls
test.txt
```
- Echo: 
```Sierra$ echo "hey guys"
hey guys```
- Put the echoed text into test.txt
```echo "hey guys" > test.txt```
- This will overwrite it.
- To append, use the operator “>>”
- echo “hello again” >> test.txt
- To see history of commands printed
`history`
- To see history in a paginator in the terminal (so that you can scroll up)
```
history | less
```
- To exit this, press “q”
- To search your history for the word “hello”
```
 history | grep "hello"
 echo "hello word" > test.txt
 echo "hello word" >> test.txt
 echo "hello again" >> test.txt
 history | grep "hello"
```
- to reverse search through your history
`Ctrl -R` 
then type in the word to search. IF YOU HIT ENTER IT WILL EXECUTE

### Copying, Renaming, and Moving Files
- Make a new directory, temp2, and two targets
```
mkdir temp2
touch target1.txt
touch target2.txt
```
- Copy target2 to a new file called target3
` cp target2.txt target-three.txt `
- Echo “hello world” into target1.txt
- Echo “hello world 2” into target2.txt 
- Copy target1 onto target2
	- You’ve overwritten the file!
	- INSTEAD: always use -i  ( a flag, “ask for confirmation before overwriting”) with cp
```
cp -i target1.txt target2.txt 
overwrite target2.txt? (y/n [n]) 
```
- Moving files
```
mv -i target-three.txt ..
```
- To rename “target-three” to “target3” when it is one directory up
```mv -i ../target-three.txt target3.txt```
- To remove a file
```
touch a_very_long_file.txt
rm -i a_very_long_file.txt 
>> remove a_very_long_file.txt? y
```
- To copy file up
```
dyn-160-39-132-68:temp2 Sierra$ cp target1.txt ../
dyn-160-39-132-68:temp2 Sierra$ cp ../target1.txt .
dyn-160-39-132-68:temp2 Sierra$ cd ..
dyn-160-39-132-68:temp Sierra$ ls
```
- To remove directory recursively
```
Sierra$ rm -ri temp2/````
dyn-160-39-132-68:temp Sierra$ rm -ri temp2/
examine files in directory temp2/? y
remove temp2//target-three.txt? y
remove temp2//target1.txt? y
remove temp2//target2.txt? y
examine files in directory temp2//trash? y
remove temp2//trash/target1.txt? y
remove temp2//trash? y
remove temp2/? y
```
- If you don’t want to iteratively remove
```Sierra$ rm -r temp2/```
- If you never want to delete, make a directory, trash, and move to trash
```
Sierra$ mv -i test.txt trash/
```
- To go back to the previous directory:
` cd -`
- NB: You can configure your prompt to be the entire path to file (and this helps you identify when you’re on your machine.

Next time: using `wget`

