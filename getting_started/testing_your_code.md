---
layout: default
title: Testing your code
nav_order: 4
has_children: true
has_toc: false
parent: Getting started
---

Testing your code
-----------------
At this point you are ready to add and update code in the repository. All committed code should come with tests. You can read about [pytest](https://docs.pytest.org/en/latest/), which should be used as the framework for testing your code. All test files should live in the `test` folder.

To run your tests:
```
python3 -m pytest -v
```