---
layout: default
title: Continuous integration
nav_order: 4
has_children: true
has_toc: false
---

# Continuous integration

Every time you push to the remote repository, a series of tasks are triggered and run using [GitHub Actions](https://github.com/features/actions). You can see this by clicking on the badge at the top of the README (or by clicking the "Actions" tab near the top of the repository). If all of the tasks pass, you will see a green "Success" icon alongside your latest commit. If you see a red "Failed" icon, one or more tasks have failed. Click on the icon to find out which task(s) have failed. On your local machine, fix the failing test(s) (using the guidance from the [getting started steps](../getting_started/getting_started.md)).

Merging any [pull requests](../pull_request/pull_request.html) into the main code base will require that all tasks are passing on `GitHub Actions`. You can see status of your checks toward the bottom of your pull request.