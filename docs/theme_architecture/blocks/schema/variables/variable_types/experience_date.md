---
layout: default
title: Experience Date
parent: Variable types
has_children: false
---

# Experience Date

Renders two select inputs. First, the creator can select an experience. Then they will be prompted to choose a slot date for the chosen experience.

Returns an [Experience Slot Calendar Date]({% link docs/reference/objects/experience_slot_calendar/date.md %}) object.

Accepts a `default` of `next_upcoming` which will select the next available date from the Creator's published experiences.

> Note: For performance reasons, the variants available via experience_date will be the 'blueprint' variant, i.e. it will have default pricing and stock levels. This does not match the specific pricing and stock for the variant on the chosen date if overrides have been applied.

##### syntax
{% raw %}
```
---
attributes:
  my_variable:
    type: experience_date
    default: next_upcoming
---

{% if my_variable %}
  {{ my_variable.experience.name }} on {{ my_variable.date | date: "%a %e %b %Y" }}
{% endif %}
```
{% endraw %}
