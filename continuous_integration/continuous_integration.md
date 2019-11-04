---
layout: default
title: Continuous integration
nav_order: 4
has_children: true
has_toc: false
---

Continuous integration
----------------------
Every time you push to the remote repository, a series of tasks are triggered and run using [CircleCI](https://circleci.com/). You can see this by clicking on the badge at the top of the README (or by clicking [here](https://circleci.com/gh/NREL/) and then navigating to the project). If all of the tasks pass, you will see a green "Success" icon alongside your latest commit on the projects `CircleCI` page. If you see a red "Failed" icon, one or more tasks have failed. Click on the icon to find out which task(s) have failed. On your local machine, fix the failing test(s) (using the guidance above).

Merging any [pull requests](pull_request/pull_request.html) into the main code base will require that all tasks are passing on `CircleCI`. You can see status of your checks toward the bottom of your pull request.