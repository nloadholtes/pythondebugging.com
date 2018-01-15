---
title: Debugging workflow
permalink: /articles/python-debugging-workflow
---

> **Rebugger**: (Noun) Someone who repeatedly commits code that causes a fixed bug to come back to life in the code base.
> 
> _"Hey, where's Tom? The client is saying the latest build is broken."_
> _"Oh, the **rebugger** took the day off."_
 
Any good General will tell you that you need a plan before you roll into battle. The same is true with computers, especially when it comes to debugging them. Having a debugging workflow is crucial to getting things done quickly.

Here is my "battle plan" that I use when I start debugging. Roughly it can be broken down into these three steps: Identify the problem, experiment & research, fix. Let's dive into specifics.

## Identify the problem
There is a wide gulf between the statements "it doesn't work" and "it's broken". Sometimes people will claim something doesn't work because it isn't doing what they expected. The first thing you need to do is establish what is the expected behavior.

### What is "expected behavior"?
Some times as a developer you will be 100% certain that your application should act the way you have coded it. But when someone else (like your boss, or the customer) uses it, they might be expecting something different and when they see what you did, they think "Oh, its broken".

Example: If a user is supposed to enter an address in a form and they only enter a zip code, you think that the app should display a box telling them all of the fields are necessary. *BUT*... the users know that the city field can and should be filled in automatically based on the zip code. So to them, the error box doesn't make sense because they already haven entered in "enough" information.

So, is this a bug?

If it is not specified in the design, then it becomes a matter of opinion. In other words it might not be a "bug", but a feature request. If it is not a bug, then it might not need to be fixed with code.

At any rate it is important to spend some time to make sure that everyone agrees on what is wrong and what it should be doing.

## Experiment & Research
Depending on how familiar you are with the code, you might find yourself skipping one or both of these steps. This is where you find the actual bug in the system and attempt to understand it.

A lot of time this step involves trying to recreate the bug and then narrowing down where in the code base it is happening. 

Some bugs will popup in one spot, but the code that caused them is actually in a different part of the code. For example, if your web page has a broken HTML table, your first thought would be that there is an issue in the template or view code. But sometimes the table HTML is actually being generated somewhere else (like in a model).

Getting into the code and finding where the bug is can be a real trial an error process. I recommend trying not to do many changes to the code at this point, but rather just read through and see if the logic lines up with what you are seeing.


## Fixing the issue
Once the steps above have been done you are finally ready for the final step, actually fixing the bug. This is the workflow I have found that is best for tackling this important job:

1. Create a branch in git (you are using version control, RIGHT?)
2. Make the actual code fix
3. Test the fix to confirm it hasn't broken anything else
4. Commit the code/make a pull request

These steps might seem like overkill, but they are critical to ensuring the quality of your code base, especially step #3. 

Too many times I have seen code fixes that break other parts of the application or that don't actually fix the bug. It is critically important to test before, during, and after.

Python has built in support for unit tests, I highly recommend using them. Specifically I like to create a test that "shows" the bug (i.e. the test code makes the bug happen, and the test fails to pass). Then I do the work to fix the bug. Once I am done and the bug is fixed, then the test should pass.

Committing the test with your code fix will make your co-workers and future developers very happy. You have increased your test coverage and provided a way to check and make sure that bug never comes back.

## Wrapping up
Don't be a rebugger. Use a good debugging workflow.

Before you start, take a minute to make a plan about what you are going to do. Then follow your plan as much as you can. The end result will be worth it when you have working code.

Bonus points if you create tests that confirm the bug is no longer there. :)
