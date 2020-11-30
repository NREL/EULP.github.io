---
layout: default
title: Distributing
nav_order: 13
has_children: true
has_toc: false
parent: Getting started
---

# Distributing

You can [generate distribution archives](https://packaging.python.org/tutorials/packaging-projects/#generating-distribution-archives) using the following commands:
```
$ python setup.py sdist bdist_wheel
```

This will create a source archive (`tar.gz`) and a built distribution (`whl`). You can then build the `whl` using the familiar `pip install` command:
```
pip install dist/*.whl
```