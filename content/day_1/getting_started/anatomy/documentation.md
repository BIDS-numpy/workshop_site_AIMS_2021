---
title: "Documentation"
draft: false
---

Documentation is an important part of any software project, especially since it's
usually the first thing that newcomers see!
It's so important in fact, that many projects have sub-projects or
teams[^1] specifically dedicated to the documentation.

#### Documentation for Python projects

Python projects typically[^2] use [Sphinx][spx] to generate the documentation.
In two sentences or less, Sphinx is a documentation generation engine that
converts the content written in a *markup language* to various other outputs,
including `html` which can then be published to the internet.
Typically, the *markup language* of choice for Python projects is
[reStructuredText](https://docutils.sourceforge.io/rst.html) (often referred
to as "r-s-t" or "rest", with a `.rst` file extension), though other
markup languages such as `markdown` can be used[^3].

One of the most important aspects of Sphinx is that it generates documentation
**directly from Python docstrings**.
This may not sound like a big deal, but it solves a huge problem in
guaranteeing that the **source code** and the **documentation** are in sync.
From a developer's perspective, this often means
**updating the documentation of a project requires modifying the source code
(in the form of docstrings).**
Therefore it is important to know how to navigate an build a project,
even if you're only interested in modifying documentation.

#### Documentation structure

Like the project itself, there are many variations between projects on how
documentation is organized, but there are some common patterns.

 - The documentation for a project lives in a documentation directory
   (most often called `doc/` or `docs/`) in the top-level of the project.
 - Within this directory, there will be a `conf.py` file[^4] which specifies
   Sphinx configuration.
 - Usually there is a build utility to help you build the documentation.
   Often times this comes in the form of a `Makefile` (or `make.bat` for Windows)
   or some other script (e.g. `pandas` has a `make.py` that should work on
   any platform).
 - Often times the documentation is organized in a directory called `source`
   or something similar, though the exact organization varies between projects.

#### Building documentation locally

It is usually recommended to build documentation locally whenever you are
making non-trivial changes, just to be sure that your changes are rendering
properly in the html output[^5].

This is usually most easily accomplished using the build utility referred to
above.
For example, both NumPy and NetworkX provide a `Makefile`, so the documentation
can be built from the `doc/` directory with:

```bash
make html
```

{{% notice info %}}
Remember - Sphinx generates documentation directly from the source code.
This means that, for projects with C-extensions, you will often have to
build the project locally in order to be able to build the documentation!
On Linux/MacOS this usually isn't much of an issue, though it may require the
installation of external build dependencies either via `conda` or the system
package manager.
Building on Windows generally tends to be more complicated.
We'll discuss building projects more
[later]({{< ref "/day_1/setting_up/dev_env_setup.md" >}})
{{% /notice %}}

Assuming the build was successful, the built html documentation will be
stored in a build directory, typically `_build/html` or `build/html`.
You can then view the results by opening the local documentation in a browser.
For example, if you cloned `networkx` to `/home/repos/networkx` and
subsequently built the documentation, view the results by opening your
favorite web browser and providing the `file://` url to the `index.html`, e.g.
`file:///home/repos/networkx/doc/build/html/index.html`.

{{% notice tip %}}
Having the documentation available locally can be particularly useful if you
are working somewhere without internet!
{{% /notice %}}

[^1]: For example, the [NumPy documentation team](https://numpy.org/devdocs/dev/howto-docs.html#documentation-team-meetings)

[^2]: As of 2021

[^3]: Support for other markup languages like markdown or [MyST][myst] is
      added using [sphinx extensions][spx-ext].

[^4]: Unfortunately it is not necessarily located in the same place for each
      project. Try `find doc/ -name conf.py`.

[^5]: reStructuredText syntax is notoriously tricky - even experienced authors
      of reST must check their work often!

[spx]: https://www.sphinx-doc.org/en/master/
[spx-ext]: https://www.sphinx-doc.org/en/master/usage/extensions/index.html
[myst]: https://myst-parser.readthedocs.io/en/latest/

