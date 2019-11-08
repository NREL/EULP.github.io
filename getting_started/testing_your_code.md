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
At this point you are ready to add/update code in the repository. Any new code should be located within a subfolder of the `name-of-code-folder` folder (e.g., within `eulpda` for EULP-data-analysis) and should come with tests. Placing your new code in the correct folder will ensure that it gets covered by test coverage, style checks, and API generation. You can read about [pytest](https://docs.pytest.org/en/latest/), which should be used as the framework for testing your code. All test files should live in the `test` folder.

To run your tests:
```
$ python3 -m pytest -v
```