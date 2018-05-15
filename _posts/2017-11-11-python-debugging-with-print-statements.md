---
title: Python Debugging With Print Statements
style: page
permalink: /articles/python-debugging-with-print-statements
tags: [python, debugging]
category: python
---

One of the most basic ways to start debugging python is to use print statements. A print statement simply puts text out to the console so you can see what's going on. This is useful for seeing what the values of certain variables, or just seeing where your program is going as an excuse. Let's look at this in a little bit more detail.

## What's the score?
For me, 99% of the time when I have a Python debug print statement it is because I want to see what value a variable has.

Thanks to Python's flexibility, sometimes we don't always pay attention to the data types we are taking in. Using a debug print statement can tell you if you are looking at the right thing, i.e. are we looking at a list, or a string? 

Also, doing a debug print can be very helpful to look at a field in an object. This is super useful if you have a dependency on a 3rd party API that is failing and you're not writing the correct value into object. 

>(Example: If your call to get an API auth token fails for some reason and you wind up storing the string "ERROR" in your token field, that would stand out like a sore thumb in a print statement.) 

In general, a light dusting of print statements on your code base can allow you to look at what the program was doing as it ran. Very useful for understanding what is and isn't happening.

## Count like Dracula
 When I am using print statements to do debugging one of the first things I like to do is put a series of numbers throughout the code. I'll put a print one at the beginning and then increment the number throughout the code in the various places where I think it is going to go. Then when I run the program I look at the output and see if I see the numbers "1" "2" "3" "4" and so on. If a number is missing the net means good chunk of code did not execute like you thought it would.

 This is useful to know because our assumptions about where the code is going aren't always correct. The only downside to this  approach is that sometimes you will find that you need to put extra numbers in between some of the numbers you put in. For example if you have print 3 and then print 4 but discovered you need to add 3 more prints take that you wind up with things like print 3a, 3B, 3C, etc.

## Loop the loop
Another spot where this helps is in testing what the values of your variables are. For example putting a print statement inside of a for Loop so that it prints out the value every time the loop goes through, can show you exactly what your values are and how they're changing.

*Fun fact: You can iterate over strings just like you can a list.* This happens to me every so often when I dig down too deep into a data structure and get a string instead of the list that holds it. Then when my loop tries to process it I wind up wondering why my logic never fires.

Having a Python debug print statement in there will quickly show that I'm looking at individual characters and not strings. After I'm done face palming it is usually pretty quick to fix (and to remove the debug print statements!).

 A bit of caution on this approach though. Print statements inside of loops can get unwieldy very quickly, and can lead to more confusion than Solutions. So use your print statements sparingly!

 Another advantage of print statement is that if your code base does not use printing as a form of logging it'll be very easy to find the print statements before you commit your code. A simple grep can reveal all the places where you have debugging code and that is very useful for keeping your code base clean. 

## Python Debug Print == win for you
Being able to do a debug print can be incredibly useful. Since print typically goes to stdout (Standard Out, aka the console) this is a location that typically will get seen, either in your development environment or in your server's production logs.

Another advantage of print is that it is built in. There's no need to install new dependencies to make this work.

> This could also be said of using the `logging` module too. 

There are other alternatives to using the humble Python debug print statement, but one should not overlook the fact that most programmers (and programming languages for that matter) learn how to do a print very early on when they are learning a new language. Since its a common point, many people understand what it is and how to use it.

## Wrapping up
print statements are a very fast and convenient way to [debug your python](https://pythondebugging.com) code as it executes. But use them sparingly otherwise you will get confused with the amount of output you have to read. 
