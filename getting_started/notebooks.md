---
layout: default
title: Notebooks
nav_order: 9
has_children: true
has_toc: false
parent: Getting started
---

Notebooks
------------
Install a kernel for your conda environment:
```
$ python -m ipykernel install --user --name <name-of-repository> --display-name <name-of-repository>
```

Open your notebook:
```
$ jupyter notebook
```

Select `Change kernel: <name-of-repository>` from the "Kernel" dropdown menu. You are now ready to import and use methods from the EULP API.

For example, for the EULP-data-analysis repository you can load classes by:
```
$ from eulpda.smart_query.EULPAthena import EULPAthena
```