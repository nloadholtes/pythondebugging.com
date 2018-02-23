---


---

<p>I’m a huge fan of dropping print or <code>logging.debug()</code> statements into my code as I debug it. But one problem with that approach is making consistent strings that you can find in your logs. If you are having this pain too, you need to check out <a href="https://github.com/gruns/icecream">IceCream</a></p>
<h2 id="show-dont-tell">Show, don’t tell!</h2>
<p>This library is a nice and very easy to use wrapper for getting data out to the console. Here’s a quick example of how to use it from their README file:</p>
<pre class=" language-python"><code class="prism  language-python"><span class="token keyword">from</span> icecream <span class="token keyword">import</span> ic

<span class="token keyword">def</span> <span class="token function">foo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">:</span>
    ic<span class="token punctuation">(</span><span class="token punctuation">)</span>
    first<span class="token punctuation">(</span><span class="token punctuation">)</span>
    
    <span class="token keyword">if</span> expression<span class="token punctuation">:</span>
        ic<span class="token punctuation">(</span><span class="token punctuation">)</span>
        second<span class="token punctuation">(</span><span class="token punctuation">)</span>
    <span class="token keyword">else</span><span class="token punctuation">:</span>
        ic<span class="token punctuation">(</span><span class="token punctuation">)</span>
        third<span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<p>Doing this allows you to see the execution of your program. The output looks like this:</p>
<pre><code>ic| example.py:4
ic| example.py:11
</code></pre>
<p>This is much easier and faster to implement than my usual go to technique of slamming <code>print("1")</code> into the code.</p>
<h2 id="why-this-is-important">Why this is important</h2>
<p>The beauty of this approach is when it is time to commit your code it is very easy to grep for <code>ic(</code> to see if you’ve got debug statements in your code. In fact, here’s some important advantages you should consider:</p>
<ul>
<li>The presense of an <code>ic()</code> statement in your code means there is debugging code</li>
<li>Using <code>ic()</code> means you don’t have to worry about interfering with your normal logging strategy (e.g. the two are separate commands with separate concerns)</li>
<li>You can easily setup a git pre-commit hook to look for these calls. If they are present, then the commit fails. (This would be next to impossible to do with print or logging statements)</li>
</ul>
<p>The end result is a cleaner codebase!</p>
<p><a href="https://github.com/gruns/icecream">https://github.com/gruns/icecream</a></p>

