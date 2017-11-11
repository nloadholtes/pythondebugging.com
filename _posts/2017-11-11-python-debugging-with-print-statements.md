---
title: Python Debugging With Print Statements
style: page
permalink: /articles/python-debugging-with-print-statements
tags: [python, debugging]
category: python
---
One of the most basic ways to start debugging python is to use print statements. A print statement simply puts text out to the console so you can see what's going on. This is useful for seeing what the values of certain variables on a, or just seeing where your program is going as an excuse. Let's look at this in a little bit more detail.

## Count like Dracula
 When I am using print statements to do debugging one of the first things I like to do is put a series of numbers throughout the code. I'll put a print one at the beginning and then increment the number throughout the code in the various places where I think it is going to go. Then when I run the program I look at the output and see if I see the numbers "1" "2" "3" "4" and so on. If a number is missing the net means good chunk of code did not execute like you thought it would.

 This is useful to know because our assumptions about where the code is going aren't always correct. The only downside to this  approach is that sometimes you will find that you need to put extra numbers in between some of the numbers you put in. For example if you have print 3 and then print 4 but discovered you need to add 3 more prints take that you wind up with things like print 3a, 3B, 3C, etc.

## Loop the loop
Another spot where this helps is in testing what the values of your variables are. For example putting a print statement inside of a for Loop so that it prints out the value every time the loop goes through, can show you exactly what your values are and how they're changing.

 A bit of caution on this approach though. Print statements inside of loops can get unwieldy very quickly, and can lead to more confusion than Solutions. So use your print statements sparingly!

 Another advantage of print statement is that if your code base does not use printing as a form of logging it'll be very easy to find the print statements before you commit your code. A simple grep can reveal all the places where you have debugging code and that is very useful for keeping your codebase clean. 

## Wrapping up
print statements are a very fast and convenient way to [debug your python](https://pythondebugging.com) code as it executes. But use them sparingly otherwise you will get confused with the amount of output you have to read. 


