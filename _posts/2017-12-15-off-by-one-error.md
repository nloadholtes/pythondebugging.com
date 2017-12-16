---
title: Python "Off by one" error 
style: page
permalink: /articles/python-off-by-one-error-range
tags: [python, debugging]
category: python
---
> *Q: What are the 3 hardest problems in computer science?*
> 
> *A: Naming things, and off by one errors.*

Let's take a look at a common off-by-one error that we see in Python all the time. The `range` function is very useful for creating a sequence that can be used in loops. Here's an example of how `range` might be used:

![range in action](https://pythondebugging.com/images/range-1.png)

We see it counted out 10 things, but it started at 0 instead of 1. In some programming languages this is the norm, but for people coming from other languages this can cause confusion.

The `range` function can also start at a specified number, and this is when the off-by-one error really tends to bite people. Recently at work we had to write a script to scan through some servers and reboot them if there was a problem.

As we fixed the servers in the cluster we had to modify our checking script so that it would skip some machines. The developer who was working on this was new to Python and this error cropped up and caused problems.

Here's a video walking through the issue. This code is a very simplified version of the code we were using. In the video I step through the code to show an approach to debugging this type of situation.

<iframe width="560" height="315" src="https://www.youtube.com/embed/b9dor6Lc9iE" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

This is of course just one example of this type of error. It also occurs frequently when you are doing `for` loops, especially over arrays that have [zero-based indexes](http://python-history.blogspot.com/2013/10/why-python-uses-0-based-indexing.html). (Javascript, C, C++, I'm looking at all of you!)

I am planning to do more posts like this. If you would like to know when a new post is up, just sign up below! *(I hate spam, so I promise I won't sell you address or anything like that.)*


<!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/horizontal-slim-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; width:100%;}
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="https://ironboundsoftware.us4.list-manage.com/subscribe/post?u=b85e98fe64eeecfe8380a6780&amp;id=49e9b07804" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Tell me more!</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_b85e98fe64eeecfe8380a6780_49e9b07804" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->
