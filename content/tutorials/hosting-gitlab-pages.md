---
title: "Hosting on GitLab Pages"
date: 2018-02-22T18:00:28-08:00
---

Hugo sites can be hosted for free on GitLab. To add a theme to a site, you
could always copy over the files into the themes/ directory and add them
directly into the git tree, but using git submodules are easier for pulling
theme updates.

Unfortunately, building with submodules is a bit tricky with GitLab's CI
system. The following instructions will allow you to use the capsule theme as a
submodule when building the site.

Note that this process is not possible on GitHub. It only supports
Jekyll-generated sites. 


## Step 1: Create .gitlab-ci.yml

At the base of your website repository, create a dotfile called
`.gitlab-ci.yml`. This file will contain the instructions for building the site
whenever new commits get pushed to it. Enter the following:

```
image: monachus/hugo

before_script:
  - git submodule init
  - git submodule update --force

pages:
  script:
    - hugo
  artifacts:
    paths:
      - public
  only:
    - master

variables:
  GIT_SUBMODULE_STRATEGY: normal
```

The instructions tell the GitLab CI system to pull an image that has Hugo and
Git installed and then build the website by running `hugo` and serving the
output in the public/ directory.


## Step 2: Mirror the capsule repository

You need to mirror Capsule on your GitLab account. You can select this option
when creating a new repository.

Note that when you mirror the repository, there will be a delay in pulling
updates made to the master repository. If this is an issue, you can always pull
the changes manually.


## Step 3: Add Capsule as a git submodule

Add Capsule as follows:
```
git submodule add ../capsule themes/capsule
```

This will make the GitLab CI system use the mirrored capsule repository when
building. This step is necessary because the CI system will not build remote
submodules. 

Note that when you build the site yourself, Hugo will look for the theme in the
../capsule directory relative to the base of your website. Put a copy there,
hard copy or symlink, or you will get build errors.
