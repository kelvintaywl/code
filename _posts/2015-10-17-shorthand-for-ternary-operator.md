---
title:  "simple shorthand for ternary operator"
date:   2015-10-17 09:00:00
description: ternary operator shorthand in JS, Python and PHP
---

Often, I have to set a variable (say `bar`) to another variable (say, `foo`)'s value, using a default value if otherwise.

In Javascript, we often do:
{% highlight javascript %}
var default = 5,
    foo = 200;
// same as:
//     var bar = foo? foo : default
var bar = foo || default;
{% endhighlight %}

In Python, it is similar to:
{% highlight python %}
default, foo = 5, 200

# same as:
#     bar = foo if foo else default 
bar = foo or default
{% endhighlight %}

Recently, I found the **nice equivalent in PHP** to be:

{% highlight php %}
$default = 5;
$foo = 20; // something truthy

// same as : 
//     $bar = $foo? $foo : $default;
$bar = $foo ?: $default;
{% endhighlight %}
