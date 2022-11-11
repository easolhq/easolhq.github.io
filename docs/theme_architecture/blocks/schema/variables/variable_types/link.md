---
layout: default
title: Link
parent: Variable types
---

# Link

Renders a link field from which a Creator can select a page, product, blog post or enter a custom url.
Returns a [Link]({% link docs/reference/objects/link.md %}) object.

##### syntax
{% raw %}
```
---
my_variable:
    type: link
    default:
        url: https://easol.com
---

<a href="{{my_variable.url}}"
    {% if my_variable.new_tab %}target="_blank" rel="noopener noreferrer"{% endif %}>
    Click here
</a>
```
{% endraw %}
