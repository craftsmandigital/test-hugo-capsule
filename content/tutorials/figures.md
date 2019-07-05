+++
title = "Figures"
date = "2017-07-31T12:50:20-04:00"
tags = ["images"]
categories = ["shortcodes"]
description = "Add figures and caption text via a shortcode."
+++

Capsule provides three shortcodes for embedding images, responsive images, and
groups of images with relevant metadata. 


## img

The `{{</* img */>}}` shortcode simply adds an img tag with the following
parameters: 

* align: aligns the image and wrap text around ('right' or 'left')
* alt (or caption): set the alt text for the image
* class: adds CSS classes to the img tag
* link: wraps the img in anchor tags so that the image has a clickable link.
  ('self' or url)
* src: the url of the image to load

If you want to center an image, use the `{{</* figure */>}}` shortcode instead.

<!-- If no values are given for height and width, Hugo will fill it in with the
size of the source image. -->

### Example 1

```text
{{</* img src="/img/logo.svg" alt="alt text" link="self" */>}}
```

{{< img src="/img/logo.svg" alt="alt text" link="self" >}}

### Example 2

```text
{{</* img src="/img/logo-info.svg" alt="alt text" link="/" align="right" */>}}
```

{{< img src="/img/logo-info.svg" alt="alt text" link="/" align="right" >}}


In 1913 I had the happy idea to fasten a bicycle wheel to a kitchen stool and
watch it turn.  A few months later I bought a cheap reproduction of a winter
evening landscape, which I called "Pharmacy" after adding two small dots, one
red and one yellow, in the horizon.  In New York in 1915 I bought at a hardware
store a snow shovel on which I wrote "In advance of the broken arm." It was
around that time that the word "Readymade" came to my mind to designate this
form of manifestation.  A point that I want very much to establish is that the
choice of these "Readymades" was never dictated by aesthetic delectation.  The
choice was based on a reaction of visual indifference with at the same time a
total absence of good or bad taste ... in fact a complete anaesthesia.  One
important characteristic was the short sentence which I occasionally inscribed
on the "Readymade." That sentence instead of describing the object like a title
was meant to carry the mind of the spectator towards other regions more verbal.
Sometimes I would add a graphic detail of presentation which, in order to
satisfy my craving for alliterations, would be called "Readymade aided." At
another time, wanting to expose the basic antinomy between art and
"Readymades," I imagined a "Reciprocal Readymade": use a Rembrandt as an
ironing board!  I realized very soon the danger of repeating indiscriminately
this form of expression and decided to limit the production of "Readymades" to
a small number yearly. I was aware at that time, that for the spectator even
more for the artist, art is a habit forming drug and I wanted to protect my
"Readymades" against such a contamination.  Another aspect of the "Readymade"
is its lack of uniqueness... the replica of the "Readymade" delivering the same
message, in fact nearly every one of the "Readymades" existing today is not an
original in the conventional sense.  A final remark to this egomaniac's
discourse: Since the tubes of paint used by an artist are manufactured and
readymade products we must conclude that all the paintings in the world are
"Readymades aided" and also works of assemblage.

### Example 3

```text
{{</* img src="/img/logo-success.svg" alt="alt text" link="/" class="image is-256x256" */>}}
```

{{< img src="/img/logo-success.svg" alt="alt text" link="/" class="image is-256x256" >}}


## figure

The `{{</* figure */>}}` shortcode overrides the default one build into Hugo.
Use it for adding single images within a `<figure>` tag. Pass it: 

* attr: author or external source to add to the caption
* attrlink: links the attr to a url
* caption (or subtitle): part of the figcaption
* class: adds CSS classes to the img tag
* link: wraps the img in anchor tags so that the image has a clickable link.
  ('self' or url)
* src: the url of the image to load
* title: part of the figcaption

### Example 1

```text
{{</* figure src="/img/logo.svg" link="self" title="Title" caption="Subtitle"
           attr="Attr. Link" attrlink="/" */>}}
```

{{< figure src="/img/logo.svg" link="self" title="Title" caption="Subtitle"
           attr="Attr Link" attrlink="/" >}}


## figure-group

The `{{</* figure-group */>}}` nests img or figure tags inside another figure
tag. Parameters: 

* attr: author or external source to add to the caption
* attrlink: links the attr to a url
* caption (or subtitle): part of the figcaption for the wrapper figure
* class: adds CSS classes to the img tag
* title: part of the figcaption for the wrapper figure


To use it, embed `{{</* figure */>}}` or `{{</* img */>}}` shortcodes inside.

### Example 1

```text
{{</* figure-group */>}}
{{</* figure src="/img/logo.svg" title="Title 1" subtitle="Subtitle 1" */>}}
{{</* figure src="/img/logo-info.svg" title="Title 2" subtitle="Subtitle 2" */>}}
{{</* /figure-group */>}}
```

{{< figure-group >}} 
{{< figure src="/img/logo.svg" title="Title 1" subtitle="Subtitle 1" >}}
{{< figure src="/img/logo-info.svg" title="Title 2" subtitle="Subtitle 2" >}}
{{< /figure-group >}}

### Example 2

```text
{{</* figure-group title="Title" subtitle="Subtitle" 
      attr="Attr link" attrlink="/" */>}}
{{</* img src="/img/logo.svg" link="/" alt="alt text" */>}}
{{</* img src="/img/logo-info.svg" link="/tutorials" alt="alt text" */>}}
{{</* img src="/img/logo-success.svg" link="/tutorials/figures/" alt="alt text" */>}}
{{</* img src="/img/logo-warning.svg" alt="alt text" */>}}
{{</* img src="/img/logo-danger.svg" alt="alt text" */>}}
{{</* /figure-group */>}}
```

{{< figure-group title="Title" subtitle="Subtitle" 
      attr="Attr link" attrlink="/" >}}
{{< img src="/img/logo.svg" link="/" alt="alt text" >}}
{{< img src="/img/logo-info.svg" link="/tutorials" alt="alt text" >}}
{{< img src="/img/logo-success.svg" link="/tutorials/figures/" alt="alt text" >}}
{{< img src="/img/logo-warning.svg" alt="alt text" >}}
{{< img src="/img/logo-danger.svg" alt="alt text" >}}
{{< /figure-group >}}

