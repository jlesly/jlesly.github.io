---
layout: post
title:      "Regular Expressions Cheat Sheet  "
date:       2020-03-23 18:26:56 +0000
permalink:  regular_expressions_cheat_sheet
---

A good way to test whether you fully understand a topic is by explaining the topic to someone who doesn't know anything about the topic. After going through the Regex lesson and lab I wanted to try to see how much I understood the basic regex patterns and I tried explaining the topic to someone who doesn't have any computer science background. 


My boyfriend is in the healthcare field and has taken an interest in my coding journey. Talking to someone who doesn't have a computer science background forces me to explain what I'm learning in the simplest terms. 

A regular expression can be used to recognize strings that follow a specific pattern. 

```
<table>
Sequence	Matches
.	Any character except newline
[xyz]	Any character listed between the brackets (x, y, and z in this example)
[a-z]	Any character between a and z, inclusive
[^xyz]	The opposite of [xyz]
\d	ASCII digits (0 through 9, inclusive)
\D	Anything except ASCII digits
\s	ASCII spaces (space, tab, newline, carriage return, form feed)
\S	Anything except ASCII spaces
<\table>
```


