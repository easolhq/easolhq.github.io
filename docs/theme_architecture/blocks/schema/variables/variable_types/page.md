---
layout: default
title: Page
parent: Variable types
---

# Page

Renders a select input from which a Creator can select a page from their site pages.
Returns a [Page]({% link docs/reference/objects/page.md %}) object.
The page variable only accepts a default of `random` which will select a random page from the Creator's published pages.

##### syntax
{% raw %}
```
---
my_variable:
    type: page
    default: random
---

{{ my_variable.url }}
```
{% endraw %}