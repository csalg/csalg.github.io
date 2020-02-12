---
layout: post
title: Python 3.7 introduces data classes
date: 2020-01-20 11:23
post-link: https://docs.python.org/3/library/dataclasses.html
---

Python 3.7 introduces this feature which is basically syntactic sugar to avoid a bunch of boilerplate when working with data classes. It creates a special `__init__` which assigns its arguments to the class fields in the order they are passed. This pattern is similar to the old collections.namedtuple...

```
@dataclass
class PageConfig:
    '''Class for keeping track of an item in inventory.'''
    title: str
    meta: str
    body: str
		section: str = "Main"
```

The API is quite extensive. An interesting feature is the [replace](https://www.youtube.com/watch?v=T-TwcmT6Rcw) function, which returns a copy of the object with some field value altered.

[This talk](https://www.youtube.com/watch?v=T-TwcmT6Rcw) goes into some detail on data classes.
