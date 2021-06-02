---
title: "Tests"
draft: false
---

The collection of all tests that are included in the software package,
often referred to collectively as the **test suite**.
The test suite is an important part of any software project, but this is
especially true for open source software.
Tests help define expected behavior, and are extremely helpful in detecting
**unexpected** behavior changes.
Any time you make a change to an existing project, you should *always* run the
test suite to check that your changes have not changed behavior in a way that
would be incompatible with the existing software[^1].

A typical workflow for changing existing code would look something like this:

 1. Setup and enter the development environment for your project.
 2. Before making any changes, **run the test suite** to ensure that everything
    is okay with your development environment.
 3. Make the change(s) as you intended.
 4. Run the test suite again to see if the changes you made have broken
    anything.
 5. Repeat steps 3-4 until you are satisfied with your change and the test
    suite passes without any unexpected failures.

#### Python testing framework

Scientific projects generally use the [pytest][pytest] testing framework to
construct the test suite.
`pytest` is a separate program that must be installed in order to run the
test suite locally.
We won't have time to go into detail on `pytest`, but we can cover a few
basic patterns:

 - Tests are defined *with the source code* in a Python package.
 - Typically, modules or packages will have an associated `tests/` directory.
   This directory will contain files typically called `test_*.py` where `*`
   refers back to the object or circumstance that is being tested[^2].
 - Within each `test_*.py`, you will find functions and/or classes that
   contain individual tests or collections of tests. These are typically named
   `test_*()` for functions or `Test*` for classes, where the `*` is a
   description of test-case or collection of test cases, respectively.

It's simpler than it sounds! Let's take a look at an example, say the
[numpy.median][np_median] function and [it's tests][np_median_tests].

#### Writing tests

Whenever you are proposing to add something new to a library (e.g. a function
or a class), you will have to **add tests** for the new functionality!
This may sound like a burden, but it is a useful and important part of the
development process.
In fact, it is often recommended that you write tests *before you write the
code for the new function itself*[^3]!
It sounds counterintuitive, but this is an effective way of laying out the
expected behavior for the new functionality.
Referring back to the development cycle at the top of the page - if you insert
a step e.g. `2a. Write tests for new function`, then following the rest of
the procedure will give you confidence that your new functionality behaves as
you expect *and* doesn't introduce unexpected changes in the rest of the library.

We won't spend too much time on the art of writing tests itself, but

#### Test coverage

A test suite is only useful if there are tests covering the expected behavior
for everything in the library!
For example, if you have a (silly) function:

```python
def foo(a: Int) -> Int:
    if a < 0:
        return abs(a)
    elif a == 0:
        raise ValueError("a can't be zero!")
    elif a < 3:
        return 3 - a
    return 2 * a
```

Then you might be tempted to write a test like:

```python
def test_foo():
    a = 6
    assert foo(a) == 12
```

and call it a day :smile:.

The problem with this is that this single test misses many different **branches**
that the function can take depending on the input value, so the behavior of
the function as a whole is not adequately tested.
A better set of tests would *at least* cover all the branches:

```python
import pytest

def test_foo_negative_input():
    assert foo(-1) == 1


def test_foo_zero_input():
    with pytest.raises(ValueError):
        foo(0)


def test_foo_gt_0_lt_3():
    assert foo(2) == 1


def test_foo_gt_3():
    assert foo(6) == 12
```

It's clear how we've improved the **test coverage** here, as we have at least
one test for each possible branch in the function.

{{% notice note %}}
We could also write tests to check the **type** of the input, though above
we've used [type annotations](https://docs.python.org/3/library/typing.html)
instead.
Using type annotations and a static type checker like
[mypy](http://mypy-lang.org/) has been
recommended since Python 3.7, though not all scientific Python libraries have
adopted type annotations yet (an opportunity for contributors :wink:).
{{% /notice %}}

This is of course a very trivial case where the branches are easy to identify ---
in practice analyzing test coverage is generally more difficult.
Fortunately there are automated tools, including a plugin for `pytest`,
[pytest-cov](https://pytest-cov.readthedocs.io/en/latest/), that automates
this process.

{{% notice tip %}}
In my opinion, checking out the test coverage of a project is
an **excellent** way to start contributing.
Coverage analysis tools like `pytest-cov` can help you identify areas in a
library where behavior is poorly defined.
In my experience, this very often leads to valuable issues where experienced
maintainers can provide insight on intended behavior, which often leads to
a better understanding of core concepts in the library.
{{% /notice %}}

It's important to note that, while important, high test coverage is not
**sufficient** to guarantee that code is well-tested!
Can you think of examples of how the tests for `foo` could be improved?

[^1]: **Backward compatibility** is an important feature for open source projects.
      Basically, it's a guarantee to users that anyone who is *using* your code
      will not have it *change unexpectedly* without warning.
[^2]: There is a lot of flexibility in how tests can be organized!
[^3]: This is often referred to as **test-driven development** or TDD.

[pytest]: https://docs.pytest.org/
[np_median]: https://github.com/numpy/numpy/blob/6790873334b143117f4e8d1f515def8c7fdeb9fb/numpy/lib/function_base.py#L3574
[np_median_tests]: https://github.com/numpy/numpy/blob/6790873334b143117f4e8d1f515def8c7fdeb9fb/numpy/lib/tests/test_function_base.py#L3308
