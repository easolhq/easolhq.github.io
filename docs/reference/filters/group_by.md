---
layout: default
title: Group By
parent: Filters
grand_parent: Reference
---

# group_by

This filter will group an array of items (such as events) by an attribute on them.

##### input
{% raw %}
```liquid
  {% assign grouped_events = events | group_by: 'time' %}
  {% for group in grouped_events %}
    <article>
      <h2>{{group.name}}</h2>

      {% for event in group.items %}
        <p>{{event.name}}</p>
      {% endfor %}
    </article>
  {% endfor %}
```
{% endraw %}

##### output
{% raw %}
```html
  <article>
    <h2>10:00</h2>

    <p>surf</p>
    <p>oneness</p>
  </article>

  <article>
    <h2>12:30</h2>

    <p>yoga</p>
  </article>
```
{% endraw %}

# group_by_expression

This filter will group an array of items, in the same way as [group_by]({% link docs/reference/filters/group_by.md %}#group_by), but will also format the attribute using the provided expression.

##### input
{% raw %}
```liquid
  {% assign grouped_events = events | group_by_exp: "event", "event.start_at | date: '%Y-%m-%d'" %}
  {% for group in grouped_events %}
    <article>
      <h2>{{group.name}}</h2>

      {% for event in group.items %}
        <p>{{event.name}}</p>
      {% endfor %}
    </article>
  {% endfor %}
```
{% endraw %}

##### output
{% raw %}
```html
  <article>
    <h2>2000-01-02</h2>

    <p>surf</p>
    <p>oneness</p>
  </article>

  <article>
    <h2>2000-01-01</h2>

    <p>yoga</p>
  </article>
```
{% endraw %}
