---
layout: default
title: Environment
nav_order: 2
has_children: true
has_toc: false
---

Environment
-----------
Source code should be written in the [Python 3.0](https://www.python.org/download/releases/3.0/) language, and stored in files with the `.py` extension. Specifically, you will need to install Python 3.6.x (this version will be [installed](../getting_started/installation.html) automatically within your environment). Keep in mind that this version of the language is _incompatible_ with the 2.x line of releases. [Notebooks](https://jupyter.org/) may be used, but only as a convenient method for calling Python classes, methods, etc. that are defined elsewhere in the source code files.

All source code `.py` files should be located within subfolders of the `name-of-code-folder` folder. For example, see the current structure of the [EULP-data-analysis code folder](https://github.com/NREL/EULP-data-analysis/tree/master/eulpda). The subfolders are `analytics`, `data_generation`, `smart_query`, etc. whereas the `name-of-code-folder` is `eulpda`. Maintaining this general structure is important because it will ensure that the API documentation format is preserved.

In general we want to be developing code that complies with Python [PEP 257](https://www.python.org/dev/peps/pep-0257/), which describes the semantics and conventions association with Python docstrings. Writing well-documented, compliant code will facilitate cleaner and more useful API documentation. For this project, [pdoc3](https://pdoc3.github.io/pdoc/) will be used to auto-generate API documentation. You do not need to worry about subversioning any API documentation; it will be generated automatically for every commit to the master branch. You can, however, generate it locally to ensure that it contains everything you believe it should. This will be explained further in the [following section](../getting_started/getting_started.md).