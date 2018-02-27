---
title: Debug Everywhere!
permalink: /articles/debug-everywhere-with-pdbe
tags: ['python', 'debugging', 'tools', 'libraries']

---
Sometimes you just want to get everything debugged and get on with your life.

But as you start to dig in you find that there's a million methods and you aren't sure which one you should start with.

Well, you are in luck! I recently discovered this cool project that will slam in `import pdb; pdb.set_trace()` at the start of every function in a given module. It is called [pdbe](https://github.com/dmytrostriletskyi/pdbe) a.k.a. "PDB Everywhere"/

This is very useful if you have a problem in a specific area of your app, for example in a `util.py` module.

**_Admit it, we all have one (or more) of those lurking in our projects..._**

This tool will throw the `set_trace()` in there and let you quickly setup a tripwire to get a debugging session started. 

Getting started is very easy, its just a `pip install pdbe` away!

> **IMPORTANT NOTE**: This library seems to by Python3 specific. But, you are doing your new development in Python3, so that shouldn't be a big deal, right? 
>  
>  _hint hint, you should be using Python 3!_


---
## But... that's a lot of code to cleanup!
The tool also comes with a handy `--clean` flag which allows you to undo those statements so that you don't accidentally commit a ton of breakpoints into your code.
> Note: Be careful, there is nothing stopping you from deploying this code, which probably would be 100 times worse than committing it into git.

---
## Speaking of git and versioning...
The tool also provides a way to track the changes it is making a git-like manner. Check out the [Advanced Usage here](https://github.com/dmytrostriletskyi/pdbe#advanced-usage) for more details.

## Go forth and debug!
So the next time you aren't sure where to start your debugging, give this library a try!

