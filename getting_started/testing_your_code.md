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
At this point you are ready to add/update code in the repository. Any new code should be located within a subfolder of the `name-of-code-folder` folder (e.g., within a subfolder of `eulpda` for EULP-data-analysis) and should have corresponding tests. Tests should execute portions of your code to ensure that actual outputs match your expected outputs.

Placing your new code in the correct folder will ensure that it gets covered by test coverage, style checks, and API generation. You can read about [pytest](https://docs.pytest.org/en/latest/), which should be used as the framework for testing your code. All test files should live in the `tests` subfolder of the repository's code folder. For example, [this](https://github.com/NREL/EULP-data-analysis/tree/master/eulpda/tests) is the folder containing all test files for EULP-data-analysis.

To run your tests:
```
$ pytest -v
```

We do not want to be subversioning any data in the repositories. The general practice would be to query once for externally-stored data (e.g., from an AWS S3 bucket), cache the data locally, and then omit subversioning that cached data folder using updates to the `.gitignore` file.