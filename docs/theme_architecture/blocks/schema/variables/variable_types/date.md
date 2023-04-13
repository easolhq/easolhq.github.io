---
layout: default
title: Date
parent: Variable types
---

# Date

Renders a date picker, from which a Creator can pick desired date.

##### Syntax

{% raw %}

```
---
my_variable:
    type: date
    array: true
    default:
      - today
---

{% for var in my_variable %}
  {{ var | date: "%s" }}
{% endfor %}
```

{% endraw %}

## Usage

By using variable with Liquid `date` filter, we can achieve:

- Date formatting: ([docs](https://shopify.github.io/liquid/filters/date/))

{% raw %}

```
---
my_variable:
    type: date
    default: today
---


<p>{{ my_variable | date: "%d" }}</p>
```

{% endraw %}

- Comparison and conditional checking:

When formatting date to epoch value (`%s`), we can compare two values with each
other.

{% raw %}

```
---
my_variable:
    type: date
    default: today
---
{% assign my_variable_epoch = my_variable | date: "%s" %}
{% assign current_date = "today" | date: "%s" %}

{% if my_variable_epoch > current_date %}
  <p>My date variable is after current date</p>
{% else %}
  <p>My date variable is before current date</p>
{% endif %}
```

{% endraw %}
