---
layout: default
title: Modifier Selection Session
parent: Objects
---

This drop is available on the post checkout selection page as `item`.
It combines the data for a particular line item with the guest information for
the user currently logged in.

# item.id

The id of the line item.

# item.title

The title of the line item.

# item.start_on

The start date of the line item.

# item.end_on

The end date of the line item.

# item.guest_id

The guest id.

# item.description

The title concatenated with the guest name, if there is a guest

# item.guest_name

The name of the guest (or guest [some number] if no name is set yet).

# item.product

If the line item product has a parent, then return that, otherwise the produc
itself (as a liquid drop)

# item.variant

The variant attached to the line item (as a liquid drop)

# item.selection_filters

An Array of
[Selection Filter]({% link docs/reference/objects/selection_filter.md  %})s.

Represents a group of filter options for this line item's variant to be
used in the post-checkout selections UI on sites.

Example usage:

{% raw %}
```liquid
{% for filter in item.selection_filters %}
  <h3>{{filter.name}}</h3>
  <ul class="filters--list">
    {% for option in filter.options %}
      <li {{option.attributes}}>{{option.name}}</li>
    {% endfor %}
  </ul>
{% endfor %}
```
{% endraw %}
