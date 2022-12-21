---
layout: default
title: Range
parent: Variable types
---

# Range

Renders a range input and returns the value selected as a string.
Accepts `min`, `max` and `step` parameters to define attributes on the input.
Has an optional `unit` value which appends a unit to the range input field, e.g. px.

##### syntax
{% raw %}
```
---
my_variable:
    type: range
    min: 0
    max: 100
    step: 10
    unit: px
    default: 50
---

{{ my_variable }}
```
{% endraw %}