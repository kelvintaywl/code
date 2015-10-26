---
title:  "try..else in Python"
date:   2015-10-26 23:50:00
description: knowing the try except block in Python more intimately
---

We know the classic try-except flow in Python. More specifally, you may also be a heavy user of the `finally:` block in this exception handling flow.

However, even cooler is the `else:` block, usually placed between `else:` and `finally:`. You can use the `else:` block to execute statements that are after the full try block is run succesfully (no exception).

Example:

{% highlight python %}
try:
	file_path = 'some/file/path/somewhere'
	infile = open(file_path)
except IOError as e:
	print('Error encountering while opening {0}: {1}'.format(file_path, e))
else:
	# some function to deal with the contents from file
	extract_some_text(infile)
finally:
	print('Closing file now...')
	infile.close()
{% endhighlight %}
