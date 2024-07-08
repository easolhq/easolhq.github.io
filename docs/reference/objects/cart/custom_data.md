---
layout: default
title: Custom Data
parent: Cart
grand_parent: Objects
---

# Custom data

The custom data the creator has chosen to be visible for this [cart]({% link docs/reference/objects/cart/index.md %}) aka booking.
Each custom data is its own array of 2 strings, the display name of the custom field & the value assigned to it. If the custom field is a checkbox, we only return the data when the checkbox is checked, with the value 'Yes'. If a Creator wants to display e.g. 'Includes a drink: true/false', they should use a multi-select data type with the options 'true' and 'false'.

##### input
{% raw %}
```liquid
{% for custom_data in cart.custom_data %}
  <p>{{ custom_data[0] }}: {{ custom_data[1] }}</p>
{% endfor %}
```
{% endraw %}

##### output
{% raw %}
```html
  <p>Assigned tour guide: Ellie</p>
  <p>Where to meet: October 10 2025, 12:15pm (local time) outside the Opera House.</p>
```
{% endraw %}
