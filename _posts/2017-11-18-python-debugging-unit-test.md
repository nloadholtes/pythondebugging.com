---
title: Python Debugging Unit Tests
style: page
permalink: /articles/python-debugging-unit-test
tags: [python, debugging, "unit test"]
category: python
---
Unit tests are a great thing to have in your code base. They allow you to check the health of your code and make sure that as you add things the original functionality stays the same. But what do you do when your unit test break? Let's look at debugging unit tests in Python.

A unit test is like any other piece of code. The only difference is the testing framework will tell you when specific parts of the code fail then continue running the rest of the tests. Typically what happens is you will either see all of your test break at once, or only a small individual test for break.

## All of the test break at once
When this happens typically something major has happened in your code base. By "major" this can be something as small as a configuration change, or perhaps a “small refactoring” that has happened that had far-reaching consequences.

When all the tests break it is best to stop and look at a diff of what has changed since the last time you ran the test.  In a perfect world you should be able to see what change happened that is causing the test break. If you're working in small commits this should be pretty easy to check using git diff. My advice on this one would be too slowly back out each change that you made until your test start working.

## Debugging single test failures
 If you have a situation where only one or two tests are failing it is pretty easy to change the test runner so that it only runs those tests. This is the best way to debug these types of problems. By running individual tests you are focusing your effort down to the area of the problem and not wasting time on running other tests.

 There are several ways to run a test individually it really depends on what testing framework you were using (nose, Pi test, unit test, Etc.). Please consult their documentation to see how to do this.

Once a single failing tests is running I will encourage you to check your Version Control to see what has changed since the last time the test was run. If it is not clear what has happened there are the best approach is to put in something like a `pdb.set_trace()` to see what is happening inside of the code. 

There are two major spots where you would put these break statements. One is in the test right before the assertion that is failing, and the other is in the actual code itself where you believe the error is occurring. I like to start by putting the break point in the unit test itself so that I can see what conditions are being set right before the code executes.

 After getting my bearings and figuring out what the unit test is doing (especially if there is complicated logic around the values that are being set before they call happens)  then I will typically either step into the python code that we are testing or I will go and put a `set_trace()` inside the code. 

## Determining where to put the set_trace()
If I know the specific spot in the python code where the problems occurring I will typically go and put the `set_trace()` statement directly there. How do you know which line to put the `set_trace()` on? If I have a stack trace, I like to start by putting it on the line before the failure. If there's no stack trace I usually check the diff and put it somewhere in there.

 Once you do this it becomes a matter of normal debugging. You step through the code you watch the value of the variables change and make your normal debugging decisions. 

 This is just a starting point, it's not necessarily the best spot to start in. At this point what we are doing is exploring a little bit to figure out what is going on. It could be that you need to actually put the set statement up a little bit higher so that you can see what variables are being set before this, or it might be necessary step into the functions that generate those values.

 If I see a stack Trace in the error report from a test that's being run, I will typically go and put the `set_trace()` statement somewhere before that line.

 "Somewhere" is kind of vague. But in all honesty it really is a very dependent on the situation of your code at that point. For example if you, if you have an error that is occurring when you make a database call putting the `set_trace()` right before the database call will only tell you what variables are being passed to the call to your database. And that point all you were doing is just seeing what was passed in you can't really affect too much of the data other than changing it directly.

## Quick alternative: using print()
Dropping into the Python debugger can be time consuming, and some cases (such as debugging threaded applications) can be difficult to do. In situations like this using the humble `print()` statement can be a great alternative.

Sprinkle `print()` statements in areas where you would normally put your `set_trace()` and you can then track the values of your variables as the code executes. When I do this, I find that looking at the output while thinking about what I was expecting to see usually helps me find the problems pretty quickly.

One more advantage of this approach: If you are using the [Python logging library](https://docs.python.org/3.6/howto/logging-cookbook.html#logging-cookbook) you could leave these `debug` statements in the code to help with future debugging or monitoring.

## Conclusion 
Debugging python unit test is a lot like debugging regular python code. The only difference is that you need to figure out how to run a individual test, then go and figure out where in the code you would put your `set_trace()` statement, and then it is normal debugging.

 In some cases you might not even need to use the `set_trace()`, you could just put in a simple print statement and probably see the information you need.

