---
layout: default
title: Code formatting
nav_order: 10
has_children: true
has_toc: false
parent: Getting started
---
Code formatting
---------------
If you find that some of your code does not conform to the style guide, use [autopep8](https://pypi.org/project/autopep8/0.8/) to automatically format your Python code. Note that this will not correct issues like unused variables.

To run autopep8:
```
$ autopep8 -i -r -a .
```
Run `flake8` again to ensure that all formatting has been corrected. If it has not, manually format your remaining Python code.