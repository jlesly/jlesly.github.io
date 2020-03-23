---
layout: post
title:      "Regular Expressions Cheat Sheet  "
date:       2020-03-23 14:26:57 -0400
permalink:  regular_expressions_cheat_sheet
---

A good way to test whether you fully understand a topic is by explaining the topic to someone who doesn't know anything about the topic. After going through the Regex lesson and lab I wanted to try to see how much I understood the basic regex patterns and I tried explaining the topic to someone who doesn't have any computer science background. 


My boyfriend is in the healthcare field and has taken an interest in my coding journey. Talking to someone who doesn't have a computer science background forces me to explain what I'm learning in the simplest terms. I put together this post to explain to him how regex works. 

A regular expression can be used to recognize strings that follow a specific pattern. 


| Character                             | Description                                                                   | Example                                    |
| --------------------------- | -------------------------------------------------- | ----------------------------- |
| non-special character     | Matches the specified characters literally       | abc matches abc, aBC        |
| (...)                                            | Capture anything matched                                     | (a)b(c) matches a and c       |
| .                                                | Any single  character	                                               | aac, abc, azc, a2c, a$c         |
| [xyz]                                       | Any character listed between the brackets      | [xyz] matches x or y or z      |
| [a-z]                                        | Any character between a through z                     | [a-z] matches a through z   |
| [^abc]                                    | Not a,b, nor c                                                                 |                                                       |
| \d                                            | Any decimal digit (0 through 9)                               | a\d matches a1, a2               |
| \D                                           | Any non-digit character                                             | a\D  matches ab                     |
| \s                                            | Any whitespace character                                        | ab\sd matches ab                 |
| \S                                           | Any non-whitespace character                               | ab\Sd matches abcd           |
| \w                                           | Any alphanumeric character                                    | Shorthand for [a-zA-Z0-9] |
| \W                                           | Any non-alphanumeric character                           |                                                     |
| {x}                                            | x repetitions                                                                    | (abc){2} matches abcabc  |
| {a,d}                                        | a through d repetitions                                               |                                                      |
| *                                               | Zero or more repetitions                                           | abc matches abc, abbcc    |
| +                                              | One or more repetitions                                            | a+c matches ac, aac, aaac |
| ?                                              | Matches the character before the ? zero or one times | ab?c matches ac,abc|
| \s                                            | Any space character                                                    | (space, \t, \r, \n)                       |
| \S                                            | Any non-whitespace character                               |                                                       |
| ^...$                                        | Starts and ends                                                             |                                                       |




