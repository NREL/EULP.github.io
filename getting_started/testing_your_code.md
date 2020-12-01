---
layout: default
title: Testing your code
nav_order: 7
has_children: true
has_toc: false
parent: Getting started
---

# Testing your code

At this point you are ready to add/update tests in the repository. Any new tests should be located within a subfolder of the `name-of-code-folder/tests` folder, e.g., within a subfolder of `eulpda/tests` for EULP-data-analysis. [This](https://github.com/NREL/EULP-data-analysis/tree/master/eulpda/tests) is the folder containing all test files for EULP-data-analysis. Tests should execute portions of your code to ensure that:
* code/scripts can be run successfully
* actual outputs match your expected outputs

You can read about [pytest](https://docs.pytest.org/en/latest/), which should be used as the framework for testing your code. 

To run your tests:
```
$ pytest -v
```