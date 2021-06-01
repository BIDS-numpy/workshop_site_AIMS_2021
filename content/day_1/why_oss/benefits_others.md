---
title: Benefits Others
draft: false
weight: 10
---

There are many ways that contributing to open-source software benefits other
researchers:

#### Accessibility

Contributing to open-source software packages makes your work accessible to
anyone with an internet connection!
 - Traditional publishing media such as scientific journals or conferences
   often require access fees or have limited attendance numbers.

#### Effective Communication

Well-written Python code is often among the most effective ways to communicate!
For example, here's the mathematical formula for a
[List-mode Maximum Likelihood Expectation Maximization][mlem_wiki] algorithm used for
image reconstruction:

![List-mode ML-EM equation](/images/mlem_eqn.png)

...and here is a basic (not particularly efficient) implementation:

```python
def compute_em_iteration(λ, α, s):
    term_one = 1 / (α @ λ)
    term_two = α.T @ term_one
    return (λ / s) * term_two
```

You be the judge on which one is easier to understand!

#### Usability

Python has an advantage over "pseudocode" in that the code is directly
executable, eliminating the need to translate from an explanation to a working example
where mistakes are often introduced.

[mlem_wiki]: https://en.wikipedia.org/wiki/Expectation%E2%80%93maximization_algorithm
