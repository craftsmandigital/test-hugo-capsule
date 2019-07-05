---
title: "Installation and Overview"
date: 2017-07-01T10:58:38-04:00
weight: 10
categories:
 - overview
tags:
 - install
 - layout
---

Capsule is a CSS-only theme for Hugo sites that uses the Bulma CSS framework
and Font-Awesome icons.


## Installation

To install Capsule, you can add it as a submodule in the `themes/` directory, or
you copy the files manually.

If you use Git to version your site, you can easily add Capsule as a submodule.
From the base of your website repository, run:

```bash
git submodule add https://github.com/sudorook/capsule themes/capsule
```

If you would instead prefer to manually install the theme, copy over the
contents of the `static/` directory to your site. Note that the CSS uses
relative paths to find the fonts, so the directory names and hierarchy must be
preserved.

Once the files are downloaded and in place, build the Hugo site with the theme.
You can either pass the `-t capsule` on the command line , or you edit this
line into your config.toml file:

```text
theme = "capsule"
```

You also should add this line to the config.toml:
```text
canonifyURLs = true
```

This is to ensure that relative paths work properly should the root of the site
be hosted in a subdirectory of the server (i.e. website.com/subdir/yoursite)
rather than the root of the front-end (i.e. website.com/yoursite).


## Building

To (re)build the CSS, you need to have npm and gulp installed. Clone the
capsule repository and once in it run:

```bash
npm install
```

and then

```bash
gulp
```

You can also enable/disable Sass components in `build/sass/capsule.sass`. You
can select which modules in Bulma get compiled by (un)commenting lines in
`build/sass/bulma/bulma.sass`, and you can tweak global variables used in
generating the CSS in `build/sass/bulma/variables.sass`.

If using using customized theme, you can maintain a fork repo and set the theme
submodule to your fork, or you can simply make a symlink in the `themes/`
directory of your site to your local repository.


## Configuration options

Capsule is set up so that Hugo automatically generate several things based on
options set in the config.toml file. Enabling or disabling them is a simple
matter of editing values for each variable.

### Automatically generate navbar menu
```text
SectionPagesMenu = "main"
```

This will cause Hugo to create a menu in the top right of the navbar visible
that shows each section on the site. (Sections are the directories within
`contents/`.) The menu appears as a dropdown list for mobile views.

It will also generate a section menu in the footer.

### Add git metadata to single pages
```text
enableGitInfo = true

[params]
  repo = "https://github.com/<user>/<repo>
```

This applies only to websites that are version controlled by git, with the
repository hosted publicly online.

With the above settings, Hugo will insert text at the bottom of each post (the
single.html layout) showing the date of the last commit for that page that
links to the specific commit in the online repository specified in the
config.toml file. Below is an example.

<p class="heading">
  Last edited:
  <a href="https://sudorook/capsule/commit/376772833702c141a2095b90e085e2eea361ed09">
    May 23, 2018
  </a>
</p>

In the config.toml, \<user\> and \<repo\> stand for the user name of your
account and the repository name of the website, respectively. The example uses
GitHub, but GitLab and any other site that follows the format of
`<siteurl>/<user>/<repo>/commit/<hash>` will work, too.

### Link to online accounts
```text
[social]
  github = "<user>"
  gitlab = "<user>"
```

Capsule is configured to automatically generate links to accounts named under
[social] in the config.toml. The links appear as buttons in the bottom-right of
the footer, opposite the search box.

The icons on each button are Font Awesome icons. The names of the sites in
under [social] in the config.toml file correspond to the Font Awesome icon
names (i.e., github and fa-github).  Capsule will correctly generate links to
your account for site with the account url format `<siteurl>/<user>` (i.e.,
github.com/username). Any sites that don't follow that format will have to be
hard-coded in the `layout/partials/footer.html` file.

### Set favicon, logo, and banner

Capsule uses four images by default:

1. favicon.ico - icon in browser tabs, etc.
2. apple-touch-icon.png - icon in browser tabs, etc.
3. logo.svg - shows up in top-left corner of the navbar beside the name of the
   website, except on the home page.
4. banner.svg - the background image for the navbar-hero on the home page.

By default, Capsule will look into the `img/` directory (assuming it exists) to
find these images.

To specify different paths or different file names, create a folder called
`data/` at the base of your website directory. Inside this directory, create a
file called data.toml. Fill it as follows:

```text
[icons]
  favicon = "/path/to/icon"
  appleicon = "/path/to/apple/icon"
  logo = "/path/to/logo"
  banner = "/path/to/banner"
```

### Add custom CSS or JS to individual pages

In Capsule, it is possible to add page-specific JS and CSS. It's more of a
hack, so bear that in mind if you use it.

In the front matter of each page (toml), add:

```text
css = """
<style>
 ...
</style>
"""

js = """
<script>
 ...
</script>
"""
```

Any content inside the style or script tags in place of the ellipsis will be
rendered or run, respectively.

### Enable Google Analytics

If you want to enable Google Analytics and have a tracking ID, add the
following to your config.toml:

```text
[params]
  googleAnalytics = "<Analytics ID>"
```

Capsule is set up so that the Analytics JS is executed on live sites, not local
(localhost) versions. Of course, this means that the site is no longer running
CSS-only.

### Enable sharing links

If you want to add a bar at the bottom of pages with a 'single' layout that
contains links to share the page with various social media sites and messaging
platforms, add the following to the config.toml:

```text
[params]
  share = true
```

Leave the variable unset or set to false to disable this.

### Set the search engine

Due to the nature of static sites, it is difficult to have an effective website
search. A simple workaround is to send queries to a standard search engine
(DuckDuckGo, Google, Bing, etc.) and limit results to those with your site URL.

By default, Capsule will use DuckDuckGo, but should you want to enter another,
add to the config.toml:

```text
[params]
  searchURL = "<baseurl>"
```

For example, `searchURL = "https://google.com"`.

### Adjust 'Related List' content

At the bottom of the page, Capsule will render a table of "Related" pages that
each has at least one tag that intersect with the set of tags on the current
page. By default, the list will only contain older pages that were published
**before** the current page, but if you want to include pages published
afterwards as well, set in the config.toml:

```text
[params]
  related = "all"
```
