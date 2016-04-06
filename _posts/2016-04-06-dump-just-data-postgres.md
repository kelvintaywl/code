---
title:  "Dump only data from tables in PostgreSQL database"
date:   2016-02-18 14:50:00
description: dump, table, postgresql
---

You can execute a dumping of your PostgreSQL database with

{% highlight postgresql %}
pg_dump -U postgres mydb > output.sql
{% endhighlight %}

However, should you just need to dump the table data (not including creating tables and schemas), you can simply use the `--data-only` option.

{% highlight postgresql %}
pg_dump -U postgres --data-only mydb > output.sql
{% endhighlight %}
