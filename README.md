Overview
--------

This repository stores __uncertainty quantification__ resources, and tracks history, for the End Use Load Profiles (EULP) project. The repository is currently a private one, meaning that contents are not visible to everyone. Only members who have been invited to the EULP-RW team have write access (and therefore read access) to the repository. Among other things, those with write access are permitted to pull and push contents from and to the repository, respectively. Users wishing to contribute to this repository should be familiar with [Git](https://git-scm.com/), the version control system software used to interact with GitHub. This [set of guides](https://guides.github.com/) provides helpful documentation and tutorials for installing and using Git, and for learning how GitHub works.

Storing our project on GitHub is important for the following reasons:
  * Files are stored remotely, and not just locally
  * EULP-RW team members can access/run everything contained in the repository
  * Development is tracked and managed (i.e., subversioned)
  * Code changes are first reviewed before they are merged into the main code base

Table of contents
-----------------
* [Overview](#overview)
* [Environment](#environment)
* [Getting started](#getting-started)
  * [Cloning the repository](#cloning-the-repository)
  * [Creating a new branch](#creating-a-new-branch)
  * [Installation](#installation)
  * [Testing your code](#testing-your-code)
  * [Checking coverage](#checking-coverage)
  * [Generating API](#generating-api)
  * [Style checking](#style-checking)
  * [Code formatting](#code-formatting)
  * [Push code](#push-code)
* [Continuous integration](#continuous-integration)
* [Pull request](#pull-request)
* [Other resources](#other-resources)

Environment
-----------
Code should be written in the [Python 3.0](https://www.python.org/download/releases/3.0/) language. Specifically, you will need to install Python 3.6 or greater (this version will be [installed](#installation) automatically within your environment). Keep in mind that this version of the language is _incompatible_ with the 2.x line of releases. [Notebooks](https://jupyter.org/) may be used, but only as a convenient method for calling Python classes, methods, etc. that are defined elsewhere in Python files.

In general we want to be developing code that complies with Python [PEP 257](https://www.python.org/dev/peps/pep-0257/), which describes the semantics and conventions association with Python docstrings. Writing well-documented, compliant code will facilitate cleaner and more useful API documentation. For this project, [pdoc3](https://pdoc3.github.io/pdoc/) will be used to auto-generate API documentation.

Getting started
---------------
Once you have become familiar with Git and GitHub, you are then ready to start contributing to this repository. The following instructions are for using Git from the command line, although there exist alternative applications for using Git and GitHub (e.g., [GitHub Desktop](https://desktop.github.com/)).
 
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
git clone git@github.com:NREL/EULP-uncertainty-quantification.git
```
Navigate into the new repository:
```
cd EULP-uncertainty-quantification
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
conda create -n eulp-uncertainty-quantification
conda activate eulp-uncertainty-quantification
```

Make sure you are using the latest version of `pip`:
```
python3 -m pip install --upgrade pip
```

Add or update any dependency packages to the `install_requires` list in `setup.py` ([this list](https://github.com/NREL/EULP-uncertainty-quantification/blob/master/setup.py#L27)). For example, maybe for the analysis `pandas` is needed for dataframe manipulation and `matplotlib` is needed for plotting. The following code block shows how to add these packages to `setup.py`.
```
install_requires=[
    'pandas',
    'matplotlib'
],
```

Install the EULP-uncertainty-quantification environment needed for this repository:
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
python3 -m coverage run --source=eulpuq -m pytest
python3 -m coverage report -m
python3 -m coverage html -d ./coverage_report
```
Generated coverage report files can be found in the `coverage_report` folder. The `index.html` will report on results at the module level, whereas the `eulpuq_*.html` files will report on results at the file level.

### Generating API
To auto-generate API documentation:
```
python3 -m pdoc --html eulpuq -o ./docs --force
mv docs/eulpuq/* docs/
rm -rf docs/eulpuq
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

Continuous integration
----------------------
Every time you push to the remote repository, a series of tasks are triggered and run using [CircleCI](https://circleci.com/). You can see this by clicking on the badge at the top of the README (or by clicking [here](https://circleci.com/gh/NREL/EULP-uncertainty-quantification)). If all of the tasks pass, you will see a green "Success" icon alongside your latest commit on the projects `CircleCI` page. If you see a red "Failed" icon, one or more tasks have failed. Click on the icon to find out which task(s) have failed. On your local machine, fix the failing test(s) (using the guidance above).

Merging any [pull requests](#pull-requests) into the main code base will require that all tasks are passing on `CircleCI`. You can see status of your checks toward the bottom of your pull request.

Pull request
------------
Once you have finished your code updates and are ready to have your changes merged into the main code base, you can then create a pull request (if you have not done so already). Assign the appropriate "Assignees" (e.g., you), "Reviewers", "Labels", etc. to the pull request. You are able to merge your branch into master once you have:
* Addressed all checklist items in the pre-populated pull request template
* Ensured you are up-to-date with the master branch
* Checked that your building is passing on `CircleCI`
* Confirmed that you have at least one pull request approval

Be sure to delete your branch after it has been merged.

As a note, every time a commit is made to the master branch the API documentation will be built. See the master branch's API documentation [here](https://nrel.github.io/EULP-uncertainty-quantification/). You can also navigate to the master branch's API documentation by clicking on the "API documentation" link at the top of the repository home page.

Other resources
---------------
Other related repositories:
* [OpenStudio-BuildStock](https://github.com/NREL/OpenStudio-BuildStock) (repository for modeling the existing building stock using OpenStudio/EnergyPlus)
* [buildstockbatch](https://github.com/NREL/buildstockbatch) (repository for running and managing batch OpenStudio-BuildStock simulations)