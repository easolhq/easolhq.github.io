---
layout: default
title: Package availability
parent: Tags
grand_parent: Reference
has_children: false
---

# Package availability

The `package_availability` tag returns an object with the package availability and price. You can optionally provide a date and guest count to evaluate against. This tag is especially useful when determining whether a package is sellable based on a customer's preferred date and guest count.

Note: All parameters are optional - you do not need to pass `adult_count`, `start_date`, or `start_time`. This is especially relevant for single-date packages, where the configured date/time is already known from the package setup.

### Example 1 - all adult counts
##### input
{% raw %}
```liquid
{% package_availability package, start_date: "2024-04-15", start_time: "11:00" %}
  {% assign any_available = result.is_available %}

  <select name="package[adult_count]">
    {% for adult_count in result.adult_counts %}
      <option value="{{ adult_count.count }}" {% unless adult_count.is_available %}disabled{% endunless %}>
        {{ adult_count.count }} {{ adult_count.count | pluralize: 'guest' }}
        {% if adult_count.is_available %}
          ({{ adult_count.price.fractional | money }})
        {% endif %}
      </option>
    {% endfor %}
  </select>
{% endpackage_availability %}
```
{% endraw %}

##### output
{% raw %}
```html
<select name="package[adult_count]">
  <option value="1">1 guest ($100)</option>
  <option value="2">2 guests ($200)</option>
  <option value="3">3 guests ($300)</option>
  <option value="4" disabled>4 guests</option>
</select>
```
{% endraw %}

### Example 2 - specify a single adult count
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

### Example 3 - no parameters (single-date package)
##### input
{% raw %}
```liquid
{% package_availability package %}
  Package is available: {{ result.is_available }}

  {% if result.is_available %}
    Total price: {{ result.price.fractional | money }}
    Per-person price: {{ result.price.per_person_fractional | money }}

    <select name="package[adult_count]">
      {% for adult_count in result.adult_counts %}
        <option value="{{ adult_count.count }}" {% unless adult_count.is_available %}disabled{% endunless %}>
          {{ adult_count.count }} {{ adult_count.count | pluralize: 'guest' }}
          {% if adult_count.is_available %}
            ({{ adult_count.price.fractional | money }})
          {% endif %}
        </option>
      {% endfor %}
    </select>
  {% endif %}
{% endpackage_availability %}
```
{% endraw %}

##### output
{% raw %}
```html
<p>Package is available: true</p>
<p>Total price: £120</p>
<p>Per-person price: £60</p>
<select name="package[adult_count]">
  <option value="1">1 guest (£60)</option>
  <option value="2">2 guests (£120)</option>
</select>
```
{% endraw %}

## Attributes

## `result.adult_counts`
{: .d-inline-block }
array of objects
{: .label .fs-1 }

This returns availability and price information for each adult count. It will return an array of objects, each containing the following methods:

### `adult_count.count`
{: .d-inline-block }
integer
{: .label .fs-1 }

The adult count.

### `adult_count.is_available`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package is available or not for this adult count. A package will be available when all its included items and required steps items (if any) have availability on the relevant date/time and the variants with availability have enough stock to accommodate the adult count, based on the quantity strategy chosen for that item when the package was put together.

- If the package is fixed-date, all relevant slots need to have enough availability for the given `adult_count`.
- If the package is multi-date, there needs to be at least one available slot for each included item and each required step.

### `adult_count.price`
{: .d-inline-block }
[Package Price]({% link docs/reference/objects/package/price.md %})
{: .label .fs-1 }

The price of the package for the adult count (total or per-person).

- If package is __sum-total__ and is __multi-date__, then the price will be the sum of the price of all slots based on the date strategy chosen for each individual item (i.e. "Closest to the calendar choice", "Exact match with calendar choice") in relation to the specified `start_date` and `start_time`.
- If package is __sum-total__ and is __fixed-date__, then the price will be the sum of the price of all slots for the given `start_date` and `start_time`.
- If the package is __custom-priced__ it will return its custom price.

## `result.is_available`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package is available or not. If the `adult_count` parameter has been provided, then this will return the availability for that adult count. Otherwise, this will return
true if any of the possible adult counts have availability.

## `result.price`
{: .d-inline-block }
[Package Price]({% link docs/reference/objects/package/price.md %})
{: .label .fs-1 }

The price of the package (total or per-person). If the `adult_count` parameter has been provided, then this will return the price for that adult count. Otherwise, this will return
the cheapest price amongst the possible adult counts that have availability.

## Parameters

It's possible to use any of the following attributes in the `package_availability` tag.

### adult_count
Optionally specify the number of guests used to look up the package availability.
If omitted or blank, the tag returns information about all possible adult counts (`result.adult_counts`).
Example: if passed "3", the tag returns availability and pricing based on whether the package has enough stock to accommodate 3 guests (with respect to the provided or inferred date/time).

### start_date
Optionally specify the date to use for availability checks (format: `YYYY-MM-DD`).
- For single-date packages, you typically do not need to provide this.
- For multi-date packages, this can be used alongside the package's date selection strategy (e.g. "Closest to the calendar choice", "Exact match with calendar choice").

### start_time
Optionally specify the time to use for availability checks (format: `HH:MM`).
- For single-date packages, you typically do not need to provide this.
- For multi-date packages, this can refine selection when the strategy uses a time component. e.g. If passed in "11:00", the package availability tag will availability information based on whether the package items will have available time slots at "11:00" on that day specified at `start_date` (if the package is fixed date or multi-date with a "Exact match with calendar choice" strategy) or relative to the "11:00" (if the package is multi date and has available upcoming time slots on the specified `start_date` when the strategy is "Closest to the calendar choice")
