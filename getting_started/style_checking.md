---
layout: default
title: Style checking
nav_order: 3
has_children: true
has_toc: false
parent: Getting started
---
Style checking
--------------
For this project, we are enforcing style guide using [Flake8](http://flake8.pycqa.org/en/latest/).

To check your code style, run:
```
python3 -m flake8 .
```
If there are any issues with your code, you will see message(s) of the form `<file-name.py>:<row-number>:<column-number>: <violation-code-and-message>`.