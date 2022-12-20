---
layout: default
title: Text
parent: Variable types
---

# Text

Renders a wysiwyg input field and returns html.

##### syntax
{% raw %}
```
---
my_variable:
    type: text
    default: <p>hello world</p>
---

{{ my_variable }}
```
{% endraw %}