---
title:  "recover code from Heroku"
date:   2016-12-17 12:40:00
description: git, heroku
---

Ideally, whenever we push our code onto Heroku, we would push it from git repositories such as in Github.
This makes cloning, managing of our code easier, separating services such as Github (code) and Heroku (deployment)

However, if you ever lost your code copy and have to recover it from Heroku:

{% highlight bash %}
heroku git:clone -a your-app-name
{% endhighlight %}
