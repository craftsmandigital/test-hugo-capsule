+++
title = "Messages"
date = "2017-07-30T11:37:28-04:00"
tags = ["text", "bulma"]
categories = ["shortcodes"]
description = "Highlight Bulma-style messages within the text."
+++

The message shortcode is a simple wrapper for the [Bulma message
class](http://bulma.io/documentation/components/message/). The syntax is:

```text
{{</* message class="<class>" title="<title>" */>}}  
content
{{</* /message */>}}  
```

{{< message title="your title" >}}
your content
{{< /message >}}

Replace \<title\> with the title of the message and \<class\> with a Bulma
class. The class markup is taken directly from the names of the Bulma classes:

1. `is-dark`
1. `is-primary`
1. `is-info`
1. `is-success`
1. `is-danger`
1. `is-warning`

If no class is specified, the message will default to something similar to the
dark version.

{{< message class="is-info" title="Note" >}}
You can specify whether the content inside the notification is rendered as
plain HTML or Markdown by using {{</* */>}} or {{%/* */%}}, respectively.
{{< /message >}}


## Examples

{{% message title="default" %}}
default
{{% /message %}}

{{< message class="is-dark" title="dark">}}
is-dark
{{< /message >}}

{{< message class="is-primary" title="primary" >}}
is-primary
{{< /message >}}

{{< message class="is-info" title="info" >}}
is-info
{{< /message >}}

{{< message class="is-success" title="success" >}}
is-success
{{< /message >}}

{{< message class="is-warning" title="warning" >}}
is-warning
{{< /message >}}

{{< message class="is-danger" title="danger" >}}
is-danger
{{< /message >}}
