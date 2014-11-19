# Week 3: Lab 
###Markdown
9/24/2014

What we discussed last time:
	- thinking about our data as vectors 
	- useful for studying the institutional context

	Blog ———————[interface, eg WordPress]————>
	Mail ————————[interface, eg Gmail]——————————>
	Wordpressing ——————[interface, eg Word]————>

Instead of having multiple different interfaces for the way we write — UNIFY them (in plain text) 
	
- what this affords us: search, preservation, encryption
- once you unify the environment — > more powerful tools! 

How to do this:
- Plain Text, Markdown, 
- Text editors — the editor does not matter
	
###Markdown formatting:
[ the key idea: you're not identifying stylistic elements, you're identifying semantic ones]

**emphasis 2**  
*emphasis 1*
#Heading
##Sub-heading
###Sub-Sub-heading
####Sub-sub-sub heading

alternatively, you can use:

Heading
===
Subheading
----


List:
- unordered one
- unordered two
- unordered three
- unordered four

1. Order list one
2. Order list two
3. Order list three

Blockquote:

>Here is my lovely blockquote of text. If I want it to go on, it will continue to be a quote until you enter a carriage return.

Here is some text, with perhaps some citation.[^1]

[^1]: Foonote number one.

Code block:
` code`  
Or you can write:
```
code code code deode coe
Useful for quoting poetry. This format preserves formatting without rendering. 

We                    could write
A little                       poem
And we're not using spaces after lines
And it's preserved like        this.
```

If you're working on say, medieval manuscript, you can use the codeblock to preserve diacritics. Or you might want to use this for including your code on how you wrote and formatted your document. 

###Tips:
- Write, don't format
- Empty space matters in Markdown
	- If you want a new line: 2 spaces and carriage return
- If you write in Markdown, you can use a renderer that takes what you have identified as a certain type of formatting
- every computer comes with an editor called "nano" which can be accessed through the Terminal 
- Better: VIM, SublimeText
- Many web intefaces will accept Markdown
- Pick your renderer depending on what you're writing for. 
	- There is a tool for doing this: Pandoc!
- Bibliography: You can connect Markdown to the .bib format
	- Eg: [@hugo_works_1907, p. 230]
	- See Dennis' [tutorial on the Programming Historian](http://programminghistorian.org/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)

YML: Yet Another Markup Language
```
- - -
title: Book  
bibliography: bib.bib  
author: Your Name  
category: this is where you put your metadata
- - -
```

###Pandoc 
- Pandoc is a universal renderer!
- you create your text in an editor and then send it to Markdown to typeset it. 
	- Say you have to be able to produce a Microsoft Word document, use pandoc!
	- Can convert to .docx
- Pandoc has a good renderer for footnotes

Using Pandoc:
- "s" = smart (will try to make reasonable assumptions about the english language, will convert -- to –– )
- "o" = guess the type of file based on the extension (which assumes the standard markdown extension, .md or .markdown)

To convert test1.md to test1.pdf  
Using "deposit line syntax"

```
pandoc -so test1.pdf test1.md
```
Alternatively, you can write
```
pandoc test1.md -s -o test1.pdf
```

If you're not in the same directory as all the files:
```
pandoc -so /Users/Sierra/pandoc-test/test1.pdf test1.md
```
