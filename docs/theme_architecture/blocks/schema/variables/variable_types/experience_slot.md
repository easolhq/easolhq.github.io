---
layout: default
title: Experience Slot
parent: Variable types
has_children: false
---

# Experience Slot

Renders two or three inputs. Firstly, the Creator selects an experience as well as a date from available dates for the chosen experience. If the experience has start times, they can then choose a time for the selected date.

Returns an [Experience Slot]({% link docs/reference/objects/product/experience_slot.md %}) object.

##### syntax
{% raw %}
```
---
attributes:
  my_variable:
    type: experience_slot
---

{% if my_variable %}
  {{ my_variable.start_on | date: "%-d %B %Y" }}{{ my_variable.start_time | date: " · %H:%M" }}
{% endif %}
```
{% endraw %}
