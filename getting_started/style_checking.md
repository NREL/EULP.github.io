---
layout: default
title: Style checking
nav_order: 7
has_children: true
has_toc: false
parent: Getting started
---
Style checking
--------------
For this project, we are enforcing style guide using [Flake8](http://flake8.pycqa.org/en/latest/). This will check for things like unused variables, bad indentations, etc.

To check your code style, run:
```
$ flake8 .
```
If there are any issues with your code, you will see message(s) of the form `<file-name.py>:<row-number>:<column-number>: <violation-code-and-message>`. You can either manually edit your source code files to correct any formatting issues, or optionally run automatic formatting as described in the [next section](code_formatting.md).