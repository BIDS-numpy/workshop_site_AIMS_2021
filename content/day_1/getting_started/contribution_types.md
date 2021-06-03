---
title: "Contribution Types"
draft: false
---

There are many different ways that one can contribute to open source projects.
In this workshop we're focused mostly on the various ways that you can
contribute **as a developer**.

### Developer Contributions

There are three main ways that you can contribute to an open source software
project as a developer:

 - Submitting new code (via pull requests)
 - Opening issues
 - Reviewing others' code

#### Submitting Pull Requests

It's obvious how submitting new code contributes to the development of a
library, though it's important to note that not every PR has to be new
functionality.
In fact, the vast majority of PRs for mature projects are not **new** functions,
but **improvements** to existing code, including new tests or clearer documentation.

#### Opening Issues

It is very common to identify problems with open source packages when you
are using them yourself, e.g. in your own personal research.
For example, you may find that the description in the docstring of a function
doesn't match the actual behavior; or that a function behaves unexpectedly for
certain input values.
It is very helpful to developers for you to draw attention to these problems
**even if you don't have the time or expertise to fix the problems yourself!**
Opening issues is the primary way that developers of projects are made aware
of problems that users are experiencing.

{{% notice note %}}
Determining *when* to open an issue is a fine balancing act: is the behavior
you're seeing truly unexpected, or are you misunderstanding something?
These types of questions are very common and it is **guaranteed** at some
point that you will open an issue that reflects your lack of understanding
rather than a real problem in the code... **and that's okay!**
On the other hand, opening a new issue shouldn't be the **first** thing you do
every time you have a question... searching the documentation and help forums
are also very important.
My personal rule of thumb is to spend at least 30 minutes researching online
myself before opening a new issue. This usually entails searching for related
issues w/ a search engine; checking the issue tracker for similar issues; and
reading the related documentation thoroughly.
Often times it helps to skim over the source code and related tests.
This due diligence benefits both yourself (you will be able to explain your
issue better) and the maintainers (reduces the chance of reporting things that
aren't actually problems).
{{% /notice %}}

#### Reviewing Code

Code review is often overlooked as a contribution type, but it can be among
the most valuable both for yourself and for the project!
We talked about the
[benefits of code review previously]({{< ref "/day_1/why_oss/benefits_you#becoming-a-better-developer" >}}), but it is often also very useful to the project itself as
reviewing code can be quite time consuming, and reviewers are often in
short supply.
It may take a bit longer to build up confidence in review, but becoming a
regular reviewer is a great way to have a outsized impact on a project!
