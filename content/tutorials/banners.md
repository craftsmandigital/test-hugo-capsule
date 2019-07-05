+++
title = "Banners"
date = "2017-07-30T22:13:57-04:00"
tags = ["images", "bulma"]
categories = ["shortcodes"]
description = "Add banners and embed images in them."
+++

The `{{</* banner */>}}` and `{{</* banner-fluid */>}}` shortcodes use the
Bulma `hero` class to display banners that can either fill the entire container
width or the entire viewport width, respectively.

Parameters: 

* title: the text to be displayed prominently in the center of the banner
* class: string of classes to add to banner
* subtitle: smaller text displayed under the title
* img: url to background image
* mode: how the image is used to fill the banner space ('stretch' or 'repeat')

Text to display in the body of the banner goes in between the `{{</* banner */>}}`
tags. 

{{< message class="is-info" title="Note" >}}
You can specify whether the content inside the notification is rendered as
plain HTML or Markdown by using {{</* ... */>}} or {{%/* ... */%}}, respectively.
{{< /message >}}

The banners can be styled based on the available Bulma classes: 

1. `is-dark`
1. `is-primary`
1. `is-info`
1. `is-success`
1. `is-warning`
1. `is-danger`

Their sizes can also be modified by adding additional Bulma classes: 

1. `is-medium`
1. `is-large`
1. `is-fullheight`


## Example 1 

```text
{{%/* banner title="Banner with Text"
    class="is-dark"
    subtitle="Subtitle" */%}}
How does one achieve eternal bliss? By saying dada. How does one become famous?  
By saying dada. With a noble gesture and delicate propriety. Till one goes  
crazy. Till one loses consciousness. How can one get rid of everything that  
smacks of journalism, worms, everything nice and right, blinkered, moralistic,  
europeanised, enervated? By saying dada. Dada is the world soul, dada is the  
pawnshop. Dada is the world's best lily-milk soap. Dada Mr Rubiner, dada Mr  
Korrodi. Dada Mr Anastasius Lilienstein. In plain language: the hospitality of  
the Swiss is something to be profoundly appreciated. And in questions of  
aesthetics the key is quality.  
{{%/* /banner */%}}
```

{{% banner title="Banner with Text"
    class="is-dark"
    subtitle="Subtitle" %}}
How does one achieve eternal bliss? By saying dada. How does one become famous?  
By saying dada. With a noble gesture and delicate propriety. Till one goes  
crazy. Till one loses consciousness. How can one get rid of everything that  
smacks of journalism, worms, everything nice and right, blinkered, moralistic,  
europeanised, enervated? By saying dada. Dada is the world soul, dada is the  
pawnshop. Dada is the world's best lily-milk soap. Dada Mr Rubiner, dada Mr  
Korrodi. Dada Mr Anastasius Lilienstein. In plain language: the hospitality of  
the Swiss is something to be profoundly appreciated. And in questions of  
aesthetics the key is quality.  
{{% /banner %}}

## Example 2

```text
{{</* banner title="Banner with Background Image"
    class="is-medium"
    subtitle="Subtitle"
    img="/img/banner.svg" mode="repeat" */>}}
{{</* /banner */>}}
```

{{< banner title="Banner with Background Image"
    class="is-medium"
    subtitle="Subtitle"
    img="/img/banner.svg" mode="repeat" >}}
{{< /banner >}}

## Example 3

```text
{{%/* banner-fluid title="Fluid Banner"
    class="is-medium is-primary"
    subtitle="Subtitle" */%}}
{{%/* /banner */%}}
```

{{% banner-fluid title="Fluid Banner"
    class="is-medium is-primary"
    subtitle="Subtitle" %}}
{{% /banner %}}
