---
title: It Benefits You
draft: false
weight: 15
---

At first glance, it may seem counter-intuitive that contributing to open
source software benefits the contributor, but this is true in many ways!
Here are just a few examples:

#### Becoming a better developer

One of the best ways to improve your own coding ability is by
[reading code written by others][read2learn].
At face value this seems like simple advice, but the first time you sit down
and try to *just read some code*, you'll realize this isn't as simple as it
seems.
Often times it is **very** difficult to understand how pieces of code within
libraries fit together; getting stuck here is very common and can be
quite discouraging.
There's also the questions of **what** to read and **how** to read effectively.
Opening up a random file and trying to read the source code like a book is
not likely to be very efficient, especially if you're not yet familiar with
the library.

A great way to get started is by participating in **reviewing pull requests.**
Pull Requests are often limited in scope and include a discussion, which
has many advantages:
 - Seeing which files have been changed helps give you a better idea of how
   everything in the library fits together.
 - Pull requests include include more *context*; i.e. the author will
   motivate and provide a brief explanation for proposed changes.
 - The discussion element is very useful, as you can ask questions or get
   feedback from suggestions.

Here are some concrete examples of things that I've personally learned from
reviewing other people's code:

 - [Language features][default_dict] that [I had never used before][nx-4640].
 - Interesting ways of accomplishing [common tasks in Python][nx-4727].

In my experience, participating in code review is one of the most effective
ways of becoming more familiar with a library and improving your own coding
ability.

#### Improvements from code review

Aside from the benefits of reviewing code written by others, there are also
obvious benefits of having your code **reviewed** by others.
When you make a contribution by opening a pull request to an open source
Python project, your submission will be reviewed by one or more project
maintainers.
In many cases, these maintainers will have a lot of experience and can help
answer questions or suggest improvements to your submission, leading to
direct improvement of your code!

#### Others building on your code

Contributing to large open source projects greatly increases the **visibility**
of your work.
For example, NumPy is used by millions of individuals ever year!
Thus you are more likely to interact with others who have similar interests
if you contribute improvements to large open-source projects.

Similarly, if you add a new feature to a library, your work benefits directly
from any improvements made by others in the future.

[read2learn]: https://betterprogramming.pub/learn-from-source-code-an-effective-way-to-grow-for-beginners-e0979e9b5a84
[default_dict]: https://docs.python.org/3/library/collections.html#collections.defaultdict
[nx-4640]: https://github.com/networkx/networkx/pull/4640
[nx-4727]: https://github.com/networkx/networkx/pull/4727#discussion_r608256314
