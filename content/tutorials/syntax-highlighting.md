+++
date = "2017-02-08T16:40:02-05:00"
title = "Syntax Highlighting"
tags = ["code", "pygments"]
categories = ["syntax"]
+++

Syntax highlighting works out-of-the-box via Hugo. Set the highlighter style in
config.toml:

```text
pygmentsstyle = "<style>"
```

For dark highlighter themes, you should rebuild capsule CSS with
`build/extra/syntax.sass`. Uncomment it from the capsule.sass file and run
`gulp`.

Without that file, the background color will default to Bulma's light
background-color, and light colored elements meant to be displayed against dark
backgrounds from dark themes will be hard to read.

Use ```` ``` ```` braces to add code blocks. To set a language-specific
highlighter, add ```` ```language```` to the opening brace, e.g.:

````text
```html
<section id="main">
  <div>
    <h1 id="title">Exercitation ullamco laboris</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
      veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
      commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
      velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
      occaecat cupidatat non proident, sunt in culpa qui officia deserunt
      mollit anim id est laborum.
    </p>
  </div>
</section>
```
````

Note that for the above to work, you also need to set in the config.toml file: 

```text
PygmentsCodeFences = true
```

## Examples

A gallery of available pygments styles is available
[here](http://blog.yjl.im/2015/08/pygments-styles-gallery.html). Below are a
few examples of available syntax highlighters, using the tango style.

### C++

```cpp
#include <iostream>
#include <cmath>

int good_log_2(int i) {
  int m=0;
  while (i>1) {
    m++;
    i=i>>1;
  }
  return m;
}

double bad_log_2(int i) {
  double inv_log_2=1.0/std::log(2.0);
  return std::log((double)i)*inv_log_2;
}

int main()
{
  for (int i=1;i<=1024;i*=2) {
    double bad_d=bad_log_2(i);
    int bad=(int)(bad_d);
    int good=good_log_2(i);
    std::cout.precision(17);
    std::cout<<" log2("<<i<<") = "<<good<<"; or "<<bad<<" from "<<bad_d<<")\n";
  }
  return 0;
}
```


### HTML

```html
<section id="main">
  <div>
    <h1 id="title">Exercitation ullamco laboris</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
      veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
      commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
      velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
      occaecat cupidatat non proident, sunt in culpa qui officia deserunt
      mollit anim id est laborum.
    </p>
  </div>
</section>
```


### Javascript

```javascript
<script>
function toCelsius(f) {
    return (5/9) * (f-32);
}

function myFunction() {
    var str = document.getElementById("demo").innerHTML; 
    var txt = str.replace(/microsoft/i,"W3Schools");
    document.getElementById("demo").innerHTML = txt;
}
</script>
```


### PHP

```php
<?php
$t = date("H");

if ($t < "20") {
    echo "Have a good day!";
} else {
    echo "Have a good night!";
}
?>
```


### Python

```python
import csv

# write stocks data as comma-separated values
writer = csv.writer(open('stocks.csv', 'wb', buffering=0))
writer.writerows([
    ('GOOG', 'Google, Inc.', 505.24, 0.47, 0.09),
    ('YHOO', 'Yahoo! Inc.', 27.38, 0.33, 1.22),
    ('CNET', 'CNET Networks, Inc.', 8.62, -0.13, -1.49)
])

# read stocks data, print status messages
stocks = csv.reader(open('stocks.csv', 'rb'))
status_labels = {-1: 'down', 0: 'unchanged', 1: 'up'}
for ticker, name, price, change, pct in stocks:
    status = status_labels[cmp(float(change), 0.0)]
    print '%s is %s (%s%%)' % (name, status, pct)
```


### Ruby

```ruby
# Simple for loop using a range.
for i in (1..4)
    print i," "
end
print "\n"

for i in (1...4)
    print i," "
end
print "\n"

# Running through a list (which is what they do).
items = [ 'Mark', 12, 'goobers', 18.45 ]
for it in items
    print it, " "
end
print "\n"

# Go through the legal subscript values of an array.
for i in (0...items.length)
    print items[0..i].join(" "), "\n"
end
```
