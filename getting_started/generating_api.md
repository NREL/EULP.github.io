---
layout: default
title: Generating API
nav_order: 3
has_children: true
has_toc: false
parent: Getting started
---
Generating API
--------------
To auto-generate API documentation:
```
python3 -m pdoc --html <name-of-code-folder> -o ./docs --force
mv docs/<name-of-code-folder>/* docs/
rm -rf docs/<name-of-code-folder>
```
Generated API documentation can be found in the `docs` folder. Like the coverage report, the `index.html` file will report on results at the module level, whereas the `*.html` files will report on results at the file level.