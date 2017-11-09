---
title: Python Debugging Environment
style: page
permalink: /articles/python-debugging-environment
tags: [python, debugging]
---

As Python developers were very fortunate that our Python debugging environment is built into our language. Pdb is the core tool that one uses when debugging python code, but there are many other nice things you can add to this to help make the job easier. 

When I begin a debugging session I like to set up my local environment to help me get through things as quickly as possible. Here are some of the tools I like to do.

## Common pdb commands
One very cool feature of pdb is the ability to save aliases and other helper functions commands that you've used in the past. There is a file called [.pdbrc](https://docs.python.org/3/library/pdb.html#debugger-commands) where you can put your commonly used shortcuts and aliases. This is kind of an advanced feature that is useful if you do a lot of debugging. 

For example, if you want to list out all the values of the attributes in a class, you could create a small function to do this and then have a shortcut to call option. This will save you a lot of typing and allow you to get your debugging session going quicker. Here are some great examples of people who have used this feature.
 
https://stackoverflow.com/questions/1614983/running-commands-from-a-file-in-pdb
https://nedbatchelder.com/blog/200704/my_pdbrc.html

## Documentation
One of the first things I like to do is have a web browser Page open to some documentation relating to the area on debugging. Usually this is the  documentation for a library like requests. It is very helpful to know what parameters can be passed into a function. Also having documentation for the core python Library handy is very used for also. There are many times where someone has ridden a chunk of code that could be replaced by something that was already in standard Library.

## Command line tools
In addition to pdb be having tools like curl, wget, or httpie are very handy to have open and ready to go. These tools specifically are for making HTTP calls into a web service. Bur debugging something it is useful to just have a small repeatable call that you can make over and over so you can look into your coat and see how it's reacting.

In addition to the built in pdb it's also very useful to have [pdb++](https://pypi.python.org/pypi/pdbpp/) installed. I'm a huge fan of this tool, it really makes the debugging sessions go faster because of its great user interface.  With color coding and syntax-highlighting, and code completion it makes Not only debugging but exploring the code a lot faster.

## IDE
If you're using an IDE like PyCharm or Eclipse then you have a certain advantage. The IDE itself will provide you with a lot of the context and you need in your environment. One major advantage is the ability to jump to code easily and quickly. When debugging sometimes you will hit a function call that you're not familiar with, and it is very useful to be able to just right click on that function and its definition.

When you are working on a large code base, or one that is unfamiliar to you, this feature of IDE's is a huge win. You will be able to move through things so much faster than you normally would.

 Setting breakpoints is also incredibly easy in an IDE and the interface it provides allows you to see a lot more details about the code and your debugging session at a high level. 

If you are able too, I highly recommended it because it can just make the whole “coding to debugging back to coding” experience much smoother. Additionally IDE’s provide frameworks for running things like unit tests which can be very handy.

## Git
This is going to sound strange but I'm a big fan of using the version-control utility git while doing debugging. The reason for this is that it allows you to make smaller atomic commits that are kept locally on your machine. 

This is useful when you want to try out several things but are unsure about actually making them permanent changes. By using git you can try out things and quickly revert them without worrying about losing your “good” changes. 

There's nothing worse than relying on your editor’s undo function because it's can only move backwards in time in One Direction. By this I mean if you make 3 different changes you can only undo back to one of them. With it git you can do a little bit more and that is just really useful if you need to try out several hypotheses.

## Wrapping up
If you are going to be doing a lot of debugging (and you always wind up doing more than you think you will), it can really pay off to have a Python debugging environment setup. This will help you get up and running faster and back to coding sooner!
