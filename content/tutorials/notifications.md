+++
title = "Notifications"
date = 2017-07-29T11:09:28-04:00
tags = ["text", "bulma"]
categories = ["shortcodes"]
description = "Add Bulma-style notifications to the text."
+++

This shortcode wraps text within a Bulma notification class. They will occupy
the container width.

Given that no JS is included, notifications cannot be dismissed unless you add
your own custom functions. These only really function to highlight text. 

To use, follow this syntax: 

```text
{{</* notification <class> */>}}
notification content
{{</* /notification */>}}
```

The available classes correspond to the class names available in Bulma:

1. `is-dark`
1. `is-primary`
1. `is-info`
1. `is-success`
1. `is-warning`
1. `is-danger`


{{< message class="is-info" title="Note" >}}
You can specify whether the content inside the notification is rendered as
plain HTML or Markdown by using {{</* */>}} or {{%/* */%}}, respectively.
{{< /message >}}

<hr>

## Examples

{{< notification >}}
default
{{< /notification >}}

{{< notification is-dark >}}
is-dark
{{< /notification >}}

{{< notification is-primary >}}
is-primary
{{< /notification >}}

{{< notification is-info >}}
is-info
{{< /notification >}}

{{< notification is-success >}}
is-success
{{< /notification >}}

{{< notification is-warning >}}
is-warning
{{< /notification >}}

{{< notification is-danger >}}
is-danger
{{< /notification >}}
