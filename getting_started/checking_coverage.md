---
layout: default
title: Checking coverage
nav_order: 3
has_children: true
has_toc: false
---
Checking coverage
-----------------
You will also want to make sure that your tests cover most or all of your code. This project uses the [Coverage.py](https://coverage.readthedocs.io/en/v4.5.x/) tool for measuring code coverage.

To generate your coverage report:
```
python3 -m coverage run --source=<name-of-code-folder> -m pytest
python3 -m coverage report -m
python3 -m coverage html -d ./coverage_report
```
Generated coverage report files can be found in the `coverage_report` folder. The `index.html` will report on results at the module level, whereas the `*.html` files will report on results at the file level.