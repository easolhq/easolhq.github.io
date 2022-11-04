---
layout: default
title: Radio
parent: Variable types
---

# Radio

Renders a radio button group and returns the value of the selected option.
Takes an `options` parameter which defines the options in the radio button group, this is an array of label, value pairs. If no `default` is specified the first `option` will be set as the initial value.

##### syntax
{% raw %}
```
---
my_variable:
    type: radio
    default: opt_1
    options:
        - label: Option 1
          value: opt_1
        - label: Option 2
          value: opt_2
---

{{my_variable}}
```
{% endraw %}