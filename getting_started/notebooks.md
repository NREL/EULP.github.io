---
layout: default
title: Notebooks
nav_order: 6
has_children: true
has_toc: false
parent: Getting started
---

# Notebooks

Notebooks are a good way to import and use classes, methods, etc. that are defined elsewhere in the source code files. Notebooks should not be used to store any source code.

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