---
title:  "custom ordering in SELECT query"
date:   2015-10-27 09:00:00
description: how to customize the ordering of rows in PostgreSQL SELECT statement
---

Let's pretend you are a SQL-savvy fitness club manager and club members sign up either for the `BRONZE`, `SILVER`, `GOLD` memberships.

Suppose the SQL table `membership` has a column `level` and it contains `BRONZE`, `SILVER`, or `GOLD` in each table row. We should have used integer values to denote the order of the membership level!

Fret not, we can still do something like this, to sort our membersip table where `BRONZE` is lowest; `GOLD` is highest.

{% highlight sql %}
SELECT *
FROM membership
ORDER BY level = "GOLD", level = "SILVER", BRONZE"
{% endhighlight %}
