---
layout: default
title: Checking coverage
nav_order: 7
has_children: true
has_toc: false
parent: Getting started
---
Checking coverage
-----------------
You will also want to make sure that your tests cover most or all of your code. This project uses the [Coverage.py](https://coverage.readthedocs.io/en/v4.5.x/) tool for measuring code coverage.

To generate your coverage report locally:
```
$ coverage run --source=<name-of-code-folder> -m pytest
$ coverage report -m
$ coverage html -d ./coverage_report
```
Locally generated coverage report files can be found within the `coverage_report` folder. The `index.html` will report on results at the module level, whereas the `*.html` files will report on results at the file level. We are not subversioning any coverage report files.