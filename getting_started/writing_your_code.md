---
layout: default
title: Writing your code
nav_order: 5
has_children: true
has_toc: false
parent: Getting started
---

# Writing your code

At this point you are ready to add/update code in the repository. Any new code should be located within a subfolder of the `name-of-code-folder` folder (e.g., within a subfolder of `eulpda` for EULP-data-analysis).

Placing your new code in the correct folder will ensure that it gets covered by test coverage, style checks, and API generation.

We do not want to be subversioning any data in the repositories. The general practice would be to query once for externally-stored data (e.g., from an AWS S3 bucket), cache the data locally, and then omit subversioning that cached data folder using updates to the `.gitignore` file.