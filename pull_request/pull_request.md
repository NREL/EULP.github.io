---
layout: default
title: Pull request
nav_order: 5
has_children: true
has_toc: false
---

# Pull request

Once you have finished your code updates and are ready to have your changes merged into the main code base, you can then create a pull request (if you have not done so already). Be sure to update the changelog (i.e., `CHANGELOG.md` located at the top level of the repository) for any new features or fixes that your pull request addresses. For the pull request, assign the appropriate "Assignees" (e.g., you), "Reviewers", "Labels", etc. to the pull request. You are able to merge your branch into develop once you have:
* Addressed all checklist items in the pre-populated pull request template
* Ensured you are up-to-date with the develop branch
* Checked that your build is passing on `CircleCI`
* Confirmed that you have at least one pull request approval

Be sure to delete your branch after it has been merged.

As a note, every time code is pushed to the master branch the API documentation and coverage report will be built and stored on static websites hosted by Amazon S3. See the master branch's API documentation and coverage report by clicking on the links located in the repository's README file.