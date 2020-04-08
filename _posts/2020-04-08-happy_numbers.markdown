---
layout: post
title:      "Happy Numbers"
date:       2020-04-08 19:15:12 -0400
permalink:  happy_numbers
---


I noticed a group of students post on Slack about the 30 day coding challenge on LeetCode and I decided to give it a try. Day two's challenge was titled Happy Numbers. Since I am still working through the beginning of the course I chose to code my answers in Ruby. 

Leetcode gave the following explanation for Happy Numbers: 

> A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.

#### **Example**

Input: 19

Output: true

Explanation: 

1^2 + 9^2 = 82

8^2 + 2^2 = 68

6^2 + 8^2 = 100

1^2 + 0^2 + 0^2 = 1



The challenge was to write an algorith to determine is a number is "happy."

A method #is_string needs to accept **n** as a parameter. 


**Solution:**
    
		def is_happy(n) 
		def add_split(num)
        arr = num.to_s.split("")
        arr.map do |str|
            str.to_i ** 2
        end.sum
    end
    i = add_split(n)
    
    until i == 1 || i == 4
        i = add_split(i)
    end
    i == 1 ? true : false
		end
    








