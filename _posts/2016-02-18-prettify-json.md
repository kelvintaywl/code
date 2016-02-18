---
title:  "prettify JSON"
date:   2016-02-18 14:50:00
description: prettify, json, curl
---

When CURL-ing HTTP requests and a json response is expected, you may prettify the JSON response (example):

{% highlight shell %}
$ curl -XGET http://example.com/api/users | python -m json.tool
{% endhighlight %}
