---
title:  "drop all rows in a table in PostgreSQL"
date:   2015-10-18 09:00:00
description: pain-free removal of all table rows via TRUNCATE
---

Let's say we have two tables, **restaurant** and **menu**, where a **menu** has a foreign key referencing **restaurant**.

To delete all records in **restaurant**, we have to DELETE FROM menu first if ON DELETE CASCADE is missing.

Or you can be a renegade, use the TRUNCATE method and feel like a champion.

{% highlight sql %}
-- dele all rows in menu, deleting any restaurant that is referenced
TRUNCATE menu CASCADE;
{% endhighlight %}


The good thing is that TRUNCATE is fast as well; unlike DELETE, it does not need to scan all rows and check for foreign-key constraints. 
More details available on [PostgreSQL documentation](http://www.postgresql.org/docs/9.1/static/sql-truncate.html).
