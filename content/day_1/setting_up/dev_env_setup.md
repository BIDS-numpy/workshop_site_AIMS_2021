---
title: "Development Environment"
draft: false
weight: 2
---

Now that we have the source code, we need to set up a development environment
in order to be able to do things like:
 - build the project
 - run the test suite / evaluate changes locally
 - build the documentation for the project

### Step 1: Installing dependencies

Most projects *depend* on other software.
Installing and managing these dependencies can be a daunting task until you're
used to it.
Fortunately, there are some straight-forward best-practices to help guide the
process.

#### Use virtual environments!

It's always a good idea to use [Python virtual environments][venv] to manage
dependencies.
The main motivation for this is that each project may have it's own set of
specific requirements.
For example, let's say you have a research project on 2D image segmentation that
requires you have numpy version 1.19 installed, but your other project on
natural language processing needs the newer numpy version 1.21.
Without virtual environments, it would be a huge pain to uninstall/reinstall
the necessary versions each time you wanted to switch between working on your
projects.

Virtual environments solve this problem by creating "sanboxes" where the
exact version of all dependencies can be stalled on a per-project basis.
This way, when you want to switch from working on image segmentation to NLP, you
only have to switch environments!

There are many different tools for creating an managing Python virtual
environments - we're not going to cover the topic in detail nor address all the
different ways.
Instead, we'll focus on two: the `venv` module (which is built into Python itself
and therefore always available) and `conda` (a popular, cross-platform package
management system).

#### Step 1a: Create a virtual environment

Let's give our virtual environment a memorable name.
Since we're going to be working on networkx in this example, we'll call it
`nx-dev`.
You can create a new, empty virtual environment as follows:

{{< tabs >}}
{{% tab name="venv" %}}
```bash
python -m venv nx-dev
```
{{% /tab %}}

{{% tab name="conda" %}}
```bash
conda create --name nx-dev
```
{{% /tab %}}
{{< /tabs >}}

{{% notice info %}}
If you are working on a project that provides an `environment.yml` file,
you can create a conda environment and install the dependencies in one step:
`conda env create -f environment.yml`
See the [conda docs on environment management][conda_env] for more details.

[conda_env]: https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
{{% /notice %}}

#### Step 1b: Activate the virtual environment

Once the environment is created, it must be activated.

{{< tabs >}}
{{% tab name="venv" %}}
```bash
source nx-dev/bin/activate
```
{{% /tab %}}

{{% tab name="conda" %}}
```bash
conda activate nx-dev
```
{{% /tab %}}
{{< /tabs >}}

You should now see the environment name in parentheses to the side of your
terminal prompt, e.g.

```console
(nx-dev) me@my-machine~$
```

#### Step 1c: Install the project dependencies

Typically, projects list their dependencies in several different ways.
The most common is to use `requirements` files.
Note that each project may handle this slightly differently - for example,
many projects have multiple different requirements files
(e.g. `test_requirements.txt` and `doc_requirements.txt`) or have a whole
`requirements` directory (like NetworkX).
Again we'll focus on the Python built-in way for installing packages(`pip`) and `conda`:

{{< tabs >}}
{{% tab name="pip" %}}
```bash
python -m pip install -r requirements.txt
```
{{% /tab %}}

{{% tab name="conda" %}}
```bash
conda install --file requirements.txt
```
{{% /tab %}}
{{< /tabs >}}

{{% notice info %}}
The above code will install the necessary dependencies needed to **install**
NetworkX and **run the test suite**.
However, the dependencies for building the documentation **are not included**!
Can you figure out how to install the extra dependencies required to
build the documentation?
*Hint: check out the files in the `requirements/` directory*
{{% /notice %}}

### Step 2: Install the project from source

Now that we have a nice virtual environment with all of the necessary
dependencies installed, we come to the final step before we can run the
development version of the project locally: building and installing.
Like everything else, there are different approaches (each with their own
nuances); we don't have time to even scratch the surface here.
Instead we'll present a basic recipe using `pip`.
You'll have plenty of time to experiment during your
[homework]({{< ref "/day_1/homework" >}}) :wink:.

From the top-level directory in the repository: `python -m pip install -e .`[^1][^2]

[^1]: The `-e` flag creates an [editable](https://pip.pypa.io/en/stable/cli/pip_install/#install-editable) mode.
[^2]: `pip` can be used to build from source within a `conda` environment.

[venv]: https://docs.python.org/3/tutorial/venv.html
