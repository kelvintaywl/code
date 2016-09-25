---
title:  "Don't Repeat Yourself in PostgreSQL with Prepared Statements"
date:   2016-09-26 01:40:00
description: postgresql, prepared statement, dry
---

Sometimes we need to perform the same queries, save for some varying values.
We can actually save the common SQL query with [prepared statements](https://www.postgresql.org/docs/9.3/static/sql-prepare.html), saving us some time.

{% highlight sql %}
PREPARE sales_revenue (int, text) AS
    SELECT SUM(price) FROM order WHERE customer_id = $1 AND order.time_created >= CURRENT_TIMESTAMP - INTERVAL $2;

EXECUTE sales_revenue(1234, '7 months');
EXECUTE sales_revenue(4567, '1 year');
{% endhighlight %}
