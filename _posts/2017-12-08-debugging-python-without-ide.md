---
title: Debugging Python without an IDE
style: page
permalink: /articles/debugging-python-without-ide
tags: [python, debugging, command line]
category: python
---
One of the best things about ideas are that they bring all of your tools together in one place. But sometimes you need to debug Python code without an IDE (Integrated Development Environment). So what do you do? That's when the command line tool [pdb](https://docs.python.org/3/library/pdb.html) comes in very very handy.

Pdb is the [Python](https://python.org) debugger and is normally a command line based utility. You can use this utility to step through your code, examine variables, and even execute small snippets of Python. I use pdb regularly to debug code on remote servers and in Docker containers. Let's look at a few of the commands that you can do in pdb to help you debug your Python.

## Basic commands
 Two of the most important commands to know about in pdb are the “l” (lowercase L) command to list out your code at the point that you're at, and the beat the backtrace command which is “bt”. These two commands will help you get oriented to where you are in your code. 

The list command shows the code at the point you are in the code this is useful to see which function and module you might be in. The backtrace command is used to show how you got to this point in the code. For example your function might have might be called from three different places, but you need to know exactly which one called it to get here at this point. By typing in “**bt**” you can see the call stack and know how it got to this point. 

 From there the next commands you need to know about is "**s**" which is the step command allows you to step through each line of code executing it and seeing what it does. You can also set breakpoints via pdb, but it is a lot harder to do than it is in the i d e. In fact this is one spot where I think that the ID is much better tool than using the command line debugger.
 
## Starting the debugger
There are two main ways to use the PDP the bugger. The first is to put a small snippet of code into your file that will trigger the the debugger when it gets hit during execution. The other way is to call your script with the debugger from the command line. I am a big fan of doing the first way so let's talk about that a little bit more.

 By putting the code: 
 
> `import pdb; pdb.set_trace()` 

 into your file and then running your code normally, the Python interpreter will start up the pdb debugger when it gets that line. Once it is started the pdb debugger allows you to do all the normal stuff I've described above. The advantage of doing it this way is that you can put the set_trace command at right at the point where you want to investigate your code.

Another way to start the debugger is to start python from the command line, and then to import pdb, and use to run your actual code. From the python documenation, this approach looks like this:

> `import pdb`
> `pdb.run('your_module.start_function')`

If you use this way to starting pdb, then you potentially have to step through a good portion of your code potentially before you get to the spot that you're trying to debug. I prefer to try and get to my problems as quickly as possible so that's why I like putting the small snippet into my code.

## Bonus: debug on error exit
An interesting alternative way to start the debugger is to start it from the command line *after* your program "exits abnormally" (this is a polite way of saying "After your code crashes"). To do this, you would type in something like:

 > `python -m pdb your_script.py`
 
 This will start your app and run it, and if it crashes (e.g. the main function returns something other that 1) it will drop into the debugger.
 
## Conclusion
 The pdb to bugger is very versatile and useful. It has a lot more features that I haven't covered here and I would encourage you to do some reading on it just to see what all it offers.. You might not need to use all of the features of has right now, but the one day you might find yourself in a situation where the more advanced commands will come in very handy!
