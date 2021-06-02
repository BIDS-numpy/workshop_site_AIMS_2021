---
title: "Getting the source code"
draft: false
weight: 1
---

The source code for scientific Python projects is managed with `git`.
Most scientific Python projects have their **main repository** available online
on GitHub; for example:

 - NumPy: https://github.com/numpy/numpy
 - SciPy: https://github.com/scipy/scipy
 - NetworkX: https://github.com/networkx/networkx
 - scikit-image: https://github.com/scikit-image/scikit-image
 - scikit-learn: https://github.com/scikit-learn/scikit-learn

#### Step 1: Fork the main repository

Start by [forking the repository][fork]. This creates a copy of the remote
repository under your own GitHub account that you can both `pull` from **and**
`push` to.

{{% notice note %}}
Not sure if you've already forked a repo? No problem! GitHub will check for
this automatically, so go ahead and click the Fork button anyway.
{{% /notice %}}

#### Step 2: Clone your fork

After forking, we have a *remote* copy of the repository that we can make
changes to.
However, it is generally much more efficient to work locally, where we have
access to our preferred tools (text editors, etc.) and can rapidly try
things out.
The easiest way to get a local copy of your fork is to `clone` it.
For example, if you've forked networkx:

```bash
git clone https://github.com/<your_user_name>/networkx.git
```

{{% notice info %}}
Be sure to replace `<your_user_name>` above with your actual GitHub user name, e.g.
`rossbar` for me!
{{% /notice %}}

This will download the repository to your system and set up a pointer to your
remote called `origin` by default:

```bash
cd networkx
git remote -v
```

#### Step 3: Add a pointer to the upstream remote

The final step in establishing links between the remotes and our local
repository is to add a pointer to the original **upstream** repository.
The upstream repository is the one that we forked from in step 1 and that we
will be making pull requests to later on.

You can call this remote pointer whatever you'd like, though by convention
it's usually referred to as "upstream":

```bash
git remote add upstream https://github.com/networkx/networkx/git
```

Adding the pointer to the upstream remote isn't strictly necessary[^1] if you're
only planning on making a quick change, but it's very useful to keep your code
up-to-date with the latest changes in the main repository.

### All set!

We now have the repository set up to be able to work locally, push our changes
to `origin` and pull any changes others have made from `upstream`.
Now let's move on to setting up a local development environment!

[^1]: Assuming there are no merge conflicts!

[fork]: https://docs.github.com/en/github/getting-started-with-github/quickstart/fork-a-repo
