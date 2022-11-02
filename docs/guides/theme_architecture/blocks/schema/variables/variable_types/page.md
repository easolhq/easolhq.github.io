---
layout: default
title: Page
parent: Variable types
---

# Page

Renders a select input from which a Creator can select a page from their site pages.
Returns a [Page]({% link docs/reference/objects/page.md %}) object.
The page variable does not accept a default.

##### syntax
{% raw %}
```
---
my_variable:
    type: page
---

{{my_variable.url}}
```
{% endraw %}