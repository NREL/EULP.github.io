---
layout: default
title: Getting started
---

Getting started
---------------
Once you have become familiar with Git and GitHub, you are then ready to start contributing to this repository. The following instructions are for using Git from the command line, although there exist alternative applications for using Git and GitHub (e.g., [GitHub Desktop](https://desktop.github.com/)):

* [Cloning the repository](#cloning-the-repository)
* [Creating a new branch](#creating-a-new-branch)
* [Installation](#installation)
* [Testing your code](#testing-your-code)
* [Checking coverage](#checking-coverage)
* [Generating API](#generating-api)
* [Style checking](#style-checking)
* [Code formatting](#code-formatting)
* [Push code](#push-code)
 
### Cloning the repository
First, create a directory for the EULP repositories on your computer.  If you do not have a preference where these repositories are located, use `/c/EULP` for Windows users and `$HOME/EULP` for macOS users.

For Windows users:
```
mkdir /c/EULP
```
For macOS users:
```
mkdir $HOME/EULP
```
Navigate to the newly created directory.

For Windows users:
```
cd /c/EULP
```
For macOS users:
```
cd $HOME/EULP
```
Clone the repository to your computer:
```
git clone git@github.com:NREL/<name-of-repository>.git
```
Navigate into the new repository:
```
cd /path/to/repository
```

### Creating a new branch
Create your own branch from master:
```
git checkout -b <new-branch-name>
```

### Installation
Download and install [conda](https://docs.conda.io/en/latest/).

Create a new conda environment:
```
conda create -n <name-of-repository>
conda activate <name-of-repository>
```

Make sure you are using the latest version of `pip`:
```
python3 -m pip install --upgrade pip
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
python3 -m pip install -e .[dev]
```

### Testing your code
At this point you are ready to add and update code in the repository. All committed code should come with tests. You can read about [pytest](https://docs.pytest.org/en/latest/), which should be used as the framework for testing your code. All test files should live in the `test` folder.

To run your tests:
```
python3 -m pytest -v
```

### Checking coverage
You will also want to make sure that your tests cover most or all of your code. This project uses the [Coverage.py](https://coverage.readthedocs.io/en/v4.5.x/) tool for measuring code coverage.

To generate your coverage report:
```
python3 -m coverage run --source=<name-of-code-folder> -m pytest
python3 -m coverage report -m
python3 -m coverage html -d ./coverage_report
```
Generated coverage report files can be found in the `coverage_report` folder. The `index.html` will report on results at the module level, whereas the `*.html` files will report on results at the file level.

### Generating API
To auto-generate API documentation:
```
python3 -m pdoc --html <name-of-code-folder> -o ./docs --force
mv docs/<name-of-code-folder>/* docs/
rm -rf docs/<name-of-code-folder>
```
Generated API documentation can be found in the `docs` folder. Like the coverage report, the `index.html` file will report on results at the module level, whereas the `*.html` files will report on results at the file level.

### Style checking
For this project, we are enforcing style guide using [Flake8](http://flake8.pycqa.org/en/latest/).

To check your code style, run:
```
python3 -m flake8 .
```
If there are any issues with your code, you will see message(s) of the form `<file-name.py>:<row-number>:<column-number>: <violation-code-and-message>`.

### Code formatting
If you find that some of your code does not conform to the style guide, use [autopep8](https://pypi.org/project/autopep8/0.8/) to automatically format your Python code.

To run autopep8:
```
python3 -m autopep8 -i -r -a .
```
Run `flake8` again to ensure that all formatting has been corrected. If it has not, manually format your remaining Python code.

### Push code
Once you have made all your code updates and all the previous tasks have been run and are passing, you are then ready to push all your commits to the remote repository. In general, [commit messages](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53) should be concise yet descriptive.