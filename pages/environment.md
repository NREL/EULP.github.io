---
layout: default
title: Environment
nav_order: 2
has_children: true
---

Environment
-----------
Code should be written in the [Python 3.0](https://www.python.org/download/releases/3.0/) language. Specifically, you will need to install Python 3.6 or greater (this version will be [installed](#installation) automatically within your environment). Keep in mind that this version of the language is _incompatible_ with the 2.x line of releases. [Notebooks](https://jupyter.org/) may be used, but only as a convenient method for calling Python classes, methods, etc. that are defined elsewhere in Python files.

In general we want to be developing code that complies with Python [PEP 257](https://www.python.org/dev/peps/pep-0257/), which describes the semantics and conventions association with Python docstrings. Writing well-documented, compliant code will facilitate cleaner and more useful API documentation. For this project, [pdoc3](https://pdoc3.github.io/pdoc/) will be used to auto-generate API documentation.