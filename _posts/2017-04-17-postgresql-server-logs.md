---
title:  "Checking queries running on local PostgreSQL server"
date:   2017-04-17 17:33:00
description: postgresql
---

If you are developing on Ubuntu (we use Ubuntu images for our virtual machines),
and would need to print / tail the executing queries against your PostgreSQL server
on your machine:

1. Update your PostgreSQL server config file to log query statements.

To find the location of your config file, you can execute this query:

{% highlight postgresql %}
SHOW config_file
{% endhighlight %}


You may look for `log_statement` setting in your config file. It is likely to be commented off. Update it to `log_statement = all` if you would like to print all statements.

2. Restart your PostgreSQL server.

3. You may start viewing / tailing the log file. By default, on Ubuntu, it is likely
to be `/var/log/postgresql/postgresql-9.3-main.log` if your PostgreSQL is installed at version 9.3 for example.
