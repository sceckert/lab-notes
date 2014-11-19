# Week 8 Lab
10/29/2014

+ Weasel Words
+ "Buddy Computing"
+ Turing Machine



### Turing Machine
- Definition: "a machine which is only capable of a finite number of conditions q1, q2, ...qn which whill be called "m-conditions" THe machine is supplied with a tyape running through it and divided into sections" (231)
- The head reads letters off a tape (in finite states -- "m configurations")
- Ex1: negation machine (Turing Machine)
	- M1: A -> !A (not A)
- Ex2: affirmation machine (TM)
	- M2: A -> A'
- What is the universal Turing machine? (Universal Turing Machine = UTM)?
	- Not only can it take symbols as an input, but it can take whole machines as input 
	- The machine can take any other turing machine as input, so it can act as both negation machine and affirmation machine
	- The difference between a calculator and a machine (using Turing's language)
	- now, the tape does not just contain information. It's able to re-write its hardware The line between hardware and software is blurry

### Turing's Paper:
- NB: Universal Turing Machine and Turing Complete Machine come in later papers. 
- NB: for turing, "effective calculabiity" = "computability" (231). 
- "We may compare a man, in the process of computing to a machine" (231) is a thought experiment, a la Wittgenstein.
	- machine is "directly aware"; "remembers" and "sees" (231) 
- The state of the machine is defined by the symbol that it is currently "aware" of"
- "If at each stage the motion of a machine is completely determined by the configuration, we shall call the machine an "automatic machine" (232).
- Self-rewriting machine
- The others are just 'rough notes to asssist the memory" 
- "The behavior of the computer at any moment is determined by the symbols which he is observing and his 'state of mind' at that moment (250).
- But then he defines it on 253 differently.  

Some questions:

- What is the software here?: Is it the operation? The "state of mind"? The symbol?
- What is the hardware?: the tape has a material substratum?
- The difference between data and program
- The data is actually part of the physical configuration

- The physical counterpart on page 253 is likened to a man who makes a note of instructions to himself
- So long as a field can be reduced to a finite set of conditions, it can be emulated. 

Weasel Words:

0. Create a new project directory.
1. Copy three of your past term papers (or anything else that you have written).
2. Convert to plain text.
3. Make a list of three "weasel words" and save to a file.
4. Write a `sed` script to replace the weasel words in place and create a backup file for safety. (this involves printing only the lines that were changed) 
5. Use `comm` or `diff` to compare the files.

Find the lines that you replaced and compare to the other
IMPORTANT NOTE:
Data Munching: destructive manipulation of data. 
- Example: the replacmenet of a word 
- Don't ever do it in place -- always dump into a new file.