---
title: Cool debugging with Ice Cream
permalink: /articles/cool-debugging-with-ice-cream
tags: ['python', 'debugging', 'tools', 'libraries']
---

I'm a huge fan of dropping `print` or `logging.debug()` statements into my code as I debug it. But one problem with that approach is making consistent strings that you can find in your logs. If you are having this pain too, you need to check out [IceCream](https://github.com/gruns/icecream)

# Show, don't tell!
This library is a nice and very easy to use wrapper for getting data out to the console. Here's a quick example of how to use it from their README file:

```python
from icecream import ic

def foo():
    ic()
    first()
    
    if expression:
        ic()
        second()
    else:
        ic()
        third()
```
Doing this allows you to see the execution of your program. The output looks like this:

```
ic| example.py:4
ic| example.py:11
```
This is much easier and faster to implement than my usual go to technique of slamming `print("1")` into the code.

# Why this is important
The beauty of this approach is when it is time to commit your code it is very easy to grep for `ic(` to see if you've got debug statements in your code. In fact, here's some important advantages you should consider:

* The presense of an `ic()` statement in your code means there is debugging code
* Using `ic()` means you don't have to worry about interfering with your normal logging strategy (e.g. the two are separate commands with separate concerns)
* You can easily setup a git pre-commit hook to look for these calls. If they are present, then the commit fails. (This would be next to impossible to do with print or logging statements)

The end result is a cleaner codebase!

But the most important reason to use this library is because of the output: with zero effort on your part you get consistent grep-able messages.

Now in you your log files (or standard out) you can quickly an easily find these special debug messages by searching for `ic|`. This makes narrowing in on your specific debugging messages much easier and faster.

# Wrapping up
Make your debugging messages stand out both in your git diffs **and** in your logging output. Use [IceCream](https://github.com/gruns/icecream
), its good for you!

