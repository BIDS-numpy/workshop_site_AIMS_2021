---
title: "Anatomy of a Python project"
draft: false
weight: 1
---

Every Python project is different, but there are some high-level features that
each will have in common.
For example, all Python projects will have a top-level **package** in which
the source code lives, as well as **documentation** and a **test suite**.
Understanding these similarities will make it easier to navigate and work on
different projects.

{{% notice tip %}}
The [Python packaging tutorial][python_packaging] is the ultimate resource for
learning more about how Python packages are structured.
It goes into much more detail than we will cover here.

[python_packaging]: https://packaging.python.org/tutorials/packaging-projects/
{{% /notice %}}

#### Python packaging

Python projects are typically composed of multiple `.py` files[^1] that are
stored in a directory in the root of the project.
This is the top-level Python **package** that contains the code and tests for
the project.

{{% notice info %}}
In most cases, the **package** name and the **repository** name are the same,
which means that the project directory and the source code directory have the
same name!
This can be confusing at first --- just remember that the outer directory
contains the **entire** project, including the documentation, license, README,
etc. while the inner directory contains the Python package, including
source code and tests.
For more information, check out the [Hitchhiker's Guide to Python][hitchhiker_structure].

[hitchhiker_structure]: https://docs.python-guide.org/writing/structure/

{{% /notice %}}

The important point here is that both the **source code** and the **tests**
are found in the top-level package.

[^1]: In many cases, projects will also include C-extensions written directly
      in C or C++, or using other popular tools such as [Cython](https://cython.org/).
