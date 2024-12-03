---
layout: default
title: Package availability
parent: Tags
grand_parent: Reference
has_children: false
---

# Package availability

The `package_availability` tag returns an object with the package availability and price for the adult count, day and time specified. Useful when determining whether a package is sellable based on a customer's choice in a calendar.

##### input
{% raw %}
```liquid
{% package_availability package, adult_count: adult_count, start_date: start_date, start_time: start_time %}

  Package is available: {{ result.is_available }}

  {% if result.is_available %}
    Total price: {{ result.price.fractional | money }}
    Per-person price: {{ result.price.per_person_fractional | money }}
  {% endif %}
{% endpackage_availability %}
```
{% endraw %}

##### output
{% raw %}
```html
<p>Package is available: true</p>
<p>Total price: £180</p>
<p>Per-person price: £60</p>
```
{% endraw %}

### `result.is_available`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package is available or not. A package will be available when all its included items and required steps items (if any) have availability on the specified date and the variants with availabilty will have enough stock to accommodate the specified adult count based on the quantity strategy chosen for that item when the package has been put toghether.

- If package is fixed date, all the slots need to have enough availability given the adult_count.
- If package is multi_date, there needs to be at least one available slot for each included item and each required step.

### `result.price`
{: .d-inline-block }
[Package Price]({% link docs/reference/objects/package/price.md %})
{: .label .fs-1 }

The price of the package (total or per-person).

- If package is __sum-total__ and is __multi-date__, then the price will be the sum of the price of all slots based on the date strategy chosen for each individual item (i.e. "Closest to the calendar choice", "Exact match with calendar choice") in relation to the specified `start_date` and `start_time`.
- If package is __sum-total__ and is __fixed-date__, then the price will be the sum of the price of all slots for the given `start_date` and `start_time`.
- If the package is __custom-priced__ it will return its custom price.

## Parameters

It's possible to use any of the following attributes in the package availability tag itself.

### adult_acount
The number of guests used to look up the package availability.
e.g If passed "3", the package avaialabilty tag will use return avaialability information based on whether the package has enough stock to accommodate 3 guests on the given `start_date` and `start_time`

### start_date
The date the package used to look up the package availability.
e.g. if passed in "2024-04-15", the package availability tag will availability information based on whether the package items will have available slots on that day (if the package is fixed date or multi-date with a "Exact match with calendar choice" strategy) or relative to the date (if the package is multi date and has available upcoming slots when the strategy is "Closest to the calendar choice")

### start_time
The date the package used to look up the package availability.
e.g. if passed in "11:00", the package availability tag will availability information based on whether the package items will have available time slots at "11:00" on that day specified at `start_date` (if the package is fixed date or multi-date with a "Exact match with calendar choice" strategy) or relative to the "11:00" (if the package is multi date and has available upcoming time slots on the specified `start_date` when the strategy is "Closest to the calendar choice")
