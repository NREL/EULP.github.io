---
layout: default
title: Installation
nav_order: 3
has_children: true
has_toc: false
parent: Getting started
---

Installation
------------
Download and install [conda](https://docs.conda.io/en/latest/).

Create a new conda environment:
```
$ conda create -n <name-of-repository>
$ conda activate <name-of-repository>
```

Going forward, the `python3` command refers to the environment variable pointing to your local install location of Python 3.0. If you do not have an environment variable set up for your Python 3.0 install, just call out the path of the Python 3.0 executable explicitly (e.g., `$ /c/Python37/python.exe`). 

Make sure you are using the latest version of `pip`:
```
$ python3 -m pip install --upgrade pip
```

Add or update any dependency packages to the `install_requires` list in `setup.py` (file located at the top level of each repository). For example, maybe for the analysis `pandas` is needed for dataframe manipulation and `matplotlib` is needed for plotting. The following code block shows how to add these packages to `setup.py`.
```
install_requires=[
    'pandas',
    'matplotlib'
],
```

Install the environment needed for this repository:
```
$ python3 -m pip install -e .[dev]
```

The previous command will install all the dependency packages that are called out in the `setup.py` file. Some of these packages are required for running things like tests and coverage, while others are required to run classes and methods found in the source code files. 