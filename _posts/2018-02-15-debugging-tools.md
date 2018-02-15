---
title: Python Debugging Tools
permalink: /articles/python-debugging-tools
tags: [python, debugging]
category: python
style: page
---
Python has many debugging tools available to help you get through your code. There are tools for working from the command line, and from IDE's, and even analysis tools that will help prevent bugs in the first place. Let's look at a few of the big ones.

##  IDE's
Integrated Development Environments (IDE) are great for getting up and going on a big project in Python.

The debugging tools for IDE's will vary from IDE to IDE, but they all typically have the same features: running the code, setting breakpoints, examining the variables.

One of the best Python IDE's today is [PyCharm](https://www.jetbrains.com/pycharm/?fromMenu). The community edition comes with everything you need to get started. There is also an awesome ecosystem of plugins that you can get to help push your Python programming to the next level.

For a really great overview of how to get up and debugging with PyCharm I highly recommend checking out this short YouTube video:
<iframe width="560" height="315" src="https://www.youtube.com/embed/QJtWxm12Eo0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

The other IDE's on the market are good too, they have a very similar workflow to PyCharm. I would encourage you to try them out (one at a time) and find the one that works best for you.

## PDB++ is the best
The best python debugging tool in my opinion is pdb. It is a command line tool that allows you to watch your code as it executes, and also examine variables. It is very useful and comes built into python. I highly recommend learning how to use it as it is very easy. 

But if you want to crank pdb to 11, you need to install [pdb++](https://pypi.python.org/pypi/pdbpp/). This easy-to-install package adds color to your debug prompt and auto completion. It makes everything in the debugging process so much more fun.

## Preventing bugs
So far we've talked a lot about "reactive" tools for finding and fixing bugs. But what if you could prevent them from happening in the first place?

This is where analysis tools come into play. Using these tools you can get a handle on where you code is going. (_hint: It isn't always a good place!_) Check out these tools to "pre-debug" your Python code:

* [Pylint](https://www.pylint.org/) -- This is a linter, it looks at your code and makes suggestions on things you could improve (like getting rid of unneeded variables, etc.)
* [pycodestyle](https://pypi.python.org/pypi/pycodestyle/) -- This tool makes recommendations about how you should format your code. It used be called `pep8`. The idea here is that if your code follows standard conventions then other Python programmers can look at your code and understand it faster.
* [flake8](https://pypi.python.org/pypi/flake8) -- This is an awesome all-in-one tool: It combines a linter with a pep8 checker. In one swoop you can get  all you need to know to make your code better!

Using these tools (especially flake8!) can point out things that can turn into bugs. I highly recommend using them early and often.

## Debugging Tools wrap-up
Of course you don't write buggy code. This post is here to help you debug other developer's Python code. ;)

There's a lot of tools out bunch of python debugging tools out there and today I showed you the best ones.

Go forth and make things work!


> Curious? Learn more about  [Python Debugging](https://pythondebugging.com/) today.v
