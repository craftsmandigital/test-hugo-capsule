---
title: "Table Of Contents"
date: 2017-07-29T11:01:35-04:00
draft: true
categories: 
 - partials
tags: 
 - layout
---

Capsule can automatically generate a table of contents for each page. Simply
set in the front matter (toml): 

```text
toc = true
```

The title from every `#` is used to generate each item in the table. The lesser
the header is in the page hierarchy, the more it will be nested. See below.

<!--more-->

## Example 1

```text
## Section 1 (h2)
...

### Section 2 (h3)
...

#### Section 3 (h4)
...

##### Section 4 (h5)
...

###### Section 5 (h6)
...

## Section 6 (h2)
...

#### Section 7 (h4)
...
```

</div>

<aside class="menu">
  <p class="menu-label">
    Table of Contents
  </p>
  <div class="menu-list">
    <nav id="TableOfContents">
    <ul>
    <li>
    <ul>
    <li><a href="#section-1-h2">Section 1 (h2)</a>
    <ul>
    <li><a href="#section-2-h3">Section 2 (h3)</a>
    <ul>
    <li><a href="#section-3-h4">Section 3 (h4)</a>
    <ul>
    <li><a href="#section-4-h5">Section 4 (h5)</a>
    <ul>
    <li><a href="#section-5-h6">Section 5 (h6)</a></li>
    </ul></li>
    </ul></li>
    </ul></li>
    </ul></li>
    <li><a href="#section-6-h2">Section 6 (h2)</a>
    <ul>
    <li>
    <ul>
    <li><a href="#section-7-h4">Section 7 (h4)</a></li>
    </ul></li>
    </ul></li>
    </ul></li>
    </ul>
  </nav>
  </div>
</aside>

<div class="content">
