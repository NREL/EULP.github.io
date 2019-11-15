---
layout: default
title: Generating API
nav_order: 6
has_children: true
has_toc: false
parent: Getting started
---
Generating API
--------------
Any time new methods, classes, etc. are added to the API, you should generate new documentation for the API. To auto-generate API documentation locally:
```
$ python3 -m pdoc --html <name-of-code-folder> -o ./docs --force
```
Generated API documentation can be found within the `docs` folder. Like the coverage report, the `index.html` file will report on results at the module level, whereas the `*.html` files will report on results at the file level.