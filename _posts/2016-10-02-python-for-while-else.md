---
title:  "for..else in Python"
date:   2016-10-02 01:40:00
description: python
---

I find myself  mostly writing a typical search function that handles unsuccessful searches in this way:

{% highlight python %}
def search(term, fn):

	for n in DB.news:
		if term in n.keywords():
			# we found a match! time to do something about it
			fn(n)
			return

	raise LookupError('search term [{}] not found in news.'.format(term))

{% endhighlight %}

However, with `for..else` in Python (`while..else` can also be used similarly), 
I can bind the handling of unsuccessful cases (no `break` or `return` statements executed in loop) in an arguably cleaner way.

{% highlight python %}
def search(term, fn):

	for n in DB.news:
		if term in n.keywords():
			# we found a match! time to do something about it
			fn(n)
			return
	else:
		raise LookupError('search term [{}] not found in news.'.format(term))

{% endhighlight %}

I recommend seeing this [discussion on StackOverflow here](http://stackoverflow.com/a/9980752)
