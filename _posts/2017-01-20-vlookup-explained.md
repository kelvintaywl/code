---
title:  "VLOOKUP function for dummies"
date:   2017-01-20 11:55:00
description: excel, spreadsheet
---

I recently got to learn how to use `VLOOKUP` and finally understood why this is a sought-after trick to know for most corporate professionals!

A quick dummy guide for those who wanna know:


{% highlight moonscript %}
=VLOOKUP(key_to_look_up, range_of_values_to_search, column_index_from_range_to_return_as_value, flag_if_approximated_is_okay)
{% endhighlight %}

Because the VLOOKUP function may return error when it cannot find a return value, it may be handy to use the `IFERROR` function like:

{% highlight moonscript %}
=IFERROR(
  VLOOKUP(key_to_look_up, range_of_values_to_search, column_index_from_range_to_return_as_value, flag_if_approximated_is_okay),
  "default value if not found"
)
{% endhighlight %}

Things to note:

- `VLOOKUP` always assume the key can be found in first column of the range to look in
- you need to also include the column from which return values are derived in the range of values to look into

I've placed an example use in a [public spreadsheet in Google](https://docs.google.com/spreadsheets/d/1U0--SfN7VpzvxQ0Cjo9KDfcUXcIVfFlESgEjG5QaJY8/edit?usp=sharing) for you to try out! 
