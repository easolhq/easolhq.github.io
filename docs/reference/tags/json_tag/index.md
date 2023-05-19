---
layout: default
title: JSON
parent: Tags
grand_parent: Reference
---
# JSON

The `json` tag allows you to define an arbitrarily complex data object using
JSON syntax.

You can render data contained in the object by navigating to it using the
familiar `.` and `[]` syntax.

This is particularly useful if you wish to reuse a partial that expects certain
objects as parameters, in a context where those objects aren't necessarily
available, like templates.

##### input
{% raw %}
```liquid
{% json test_object %}
{ 
  "hello": "world",
  "array": [
    1,
    2,
    3,
    { "nested": "object" }
  ]
}
{% endjson %}

{{ test_object.hello }}
{{ test_object.array[3].nested }}
```
{% endraw %}

##### output
{% raw %}
```html
world
object
```
{% endraw %}

You may also evaluate Liquid expressions inside the `json` block, like so:

##### input

{% raw %}
```liquid
{% json test_object %}
{ "evaluate_this": {{ 2 | times: 2 }} }
{% endjson %}

{{ test_object.evaluate_this }}
```
{% endraw %}

##### output
{% raw %}
```html
4
```
{% endraw %}
