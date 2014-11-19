# Week 7 Class Notes
10/22/2014 and 10/24/2014

## Hunting the Whale | Code and Poetry 2014

Using the commands you have learned so far, solve the following problem. This is easier done in several lines.

Goal: Analyze treatment of animals in Herman Melville's *Moby Dick*.

### Pseudo-code
0. Create a project directory.
`mkdir project/
wget https://raw.githubusercontent.com/denten-courses/code-poetry/master/2014-fall/assignments/hunting-moby.md`
1. Grab the text of the novel.[^2]
```
cd project  
wget http://www.gutenberg.org/cache/epub/2701/pg2701.txt
```

2. Make two lists: one of words related to humans, one to animals.
```
touch animals.txt
touch humans.txt
```
3. Find all those words in the text, grab context, and save to file.
```
grep -w -f humans.txt pg2701.txt >> human_context.txt
grep -w -f animals.txt pg2701.txt >> animal_context.txt
 ```
4. Separate lines into words (tokenize). Make new files that contain word lists.
```
sed -e 's/ /\'$'\n/g' human_context.txt >> human_context_tokenized.txt
sed -e 's/ /\'$'\n/g' animal_context.txt >> animal_context_tokenized.txt
```
5. Remove punctuation.
```
cat animal_context_tokenized.txt | tr -d '[:punct:]' >> animal_context_tokenized_new.txt
cat human_context_tokenized.txt | tr -d '[:punct:]' >> human_context_tokenized_new.txt
```

6. Make a print out of all the words that are in File A but not in file B and the other way around.
```
man grep
grep -v -f  animal_context_tokenized_new.txt human_context_tokenized_new.txt >> words_in_humans_not_animals.txt | cat words_in_animals_not_humans.txt
```
```
grep -v -f  human_context_tokenized_new.txt animal_context_tokenized_new.txt  >> words_in_animals_not_humans.txt | cat words_in_humans_not_animals.txt
```


### Code

Grab the source code for this document.[^1] Add your step-by step solution (every command, including `mkdir`). Use pandoc to convert to `.pdf`. Submit as a `.pdf` file to Piazza. Feel free to ask for help on the forum!

[^1]: <https://raw.githubusercontent.com/denten-courses/code-poetry/master/2014-fall/assignments/hunting-moby.md?>
[^2]: <http://www.gutenberg.org/cache/epub/2701/pg2701.txt>

Group for [XP methods](http://xpmethod.github.io/research.html)
- Talk series on Method. 
- rethinking publishing & public discourse
- minimal computing - (computing globally; equity of access)

===============
## Class notes:

Minimal Viable Citizen (an offshoot of minimal computing)
- What are the minimal tools and practices you need to know to be a citizen in the digital world?
- Making lab notebooks into tutorial, then compile all of these into a website. 
- We'll make a site (and also talk about what is required to publish something together with other people)
	- How to collaborate well.
	- If you want to get involved in an open source project.
- get into the habit of pruning and cleaning lab notebooks
- When you learn something new: dump history file, then edit it.
- On Denis' site, [list of journals and conferences](https://github.com/denten/dhnotes/wiki/journals) 

On the assignment:
- pseudocode and code:
	- a way to break up larger concepts
	- taking a big problem and writing down a step by step algorithm.


### Assignment 2
Weasel Words: take a piece of writing that you wrote and check with clarity 
- create directory
- copy 3 papers that you wrote into this directory
- make these files plain text
- make a list of 3 "weasel words": words that you hate in writing, words that good writers shouldn't be using
- write a script that replaces these weasel words with something, e.g. a space, etc.

Tip: If you look at the `grep` manual, you will see that it can take a file as an attribute (so one could use the female.txt or male.txt)
- `grep -f` will obtain patterns from a file. 