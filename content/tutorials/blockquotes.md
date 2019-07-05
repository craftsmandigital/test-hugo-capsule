+++
title = "Blockquotes"
date = "2017-07-30T22:15:49-04:00"
tags = ["text"]
categories = ["shortcodes"]
description = "Embed quotes in blockquotes and add custom markup for author, date, etc."
+++

Use the `{{</* blockquote */>}}` shortcode to highlight blocks of text and also
add metadata.

Parameters: 

* author: source author, appears as the title in the blockquote footer
* source: book, context, etc. where the text is derived, appearing as a
  subtitle below the author in the footer
* date: also appears as subtitle in the footer

{{< message class="is-info" title="Note" >}}
You can specify whether the content inside the notification is rendered as
plain HTML or Markdown by using {{</* */>}} or {{%/* */%}}, respectively.
{{< /message >}}


```text
{{</* blockquote date="27 March 1920" author="Francis Picabia" 
    source="Manifeste cannibale dada" */>}}
You are all indicted; stand up! Stand up as you would for the Marseillaise or
God Save the King....  
Dada alone does not smell: it is nothing, nothing, nothing.  

    It is like your hopes: nothing.  
    like your paradise: nothing.  
    like your idols: nothing.  
    like your politicians: nothing.  
    like your heroes: nothing.  
    like your artists: nothing.  
    like your religions: nothing.  

Hiss, shout, kick my teeth in, so what? I shall still tell you that you are
half-wits. In three months my friends and I will be selling you our pictures
for a few francs.
{{</* /blockquote */>}}
```

{{< blockquote date="27 March 1920" author="Francis Picabia"
    source="Manifeste cannibale dada" >}}
You are all indicted; stand up! Stand up as you would for the Marseillaise or
God Save the King....  
Dada alone does not smell: it is nothing, nothing, nothing.  

    It is like your hopes: nothing.  
    like your paradise: nothing.  
    like your idols: nothing.  
    like your politicians: nothing.  
    like your heroes: nothing.  
    like your artists: nothing.  
    like your religions: nothing.  

Hiss, shout, kick my teeth in, so what? I shall still tell you that you are
half-wits. In three months my friends and I will be selling you our pictures
for a few francs.
{{< /blockquote >}}
