---
layout: default
title: Accommodation availability
parent: Tags
grand_parent: Reference
has_children: false
---

# Accommodation availability

The `accommodation_availability` tag returns an array of [Availability Day]({% link docs/reference/objects/product/variant/accommodation_variant/availabilty_day.md %}) objects—one per calendar day in a range for the specified [variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).

By default the range is the **first calendar month that contains any availability** for the variant. You can extend how many months are included with `number_of_months`, or set an explicit inclusive window with `start_date` and `end_date` (for example, package check-in and check-out dates).

##### input
{% raw %}
```liquid
{% accommodation_availability variant %}
  {% for day in result.days %}
       <time data-available="{{ day.available }}" datetime="{{ day.date }}">{{ day.date | date:"%b %d, %y" }}</time>
  {% endfor %}
{% endaccommodation_availability %}
```
{% endraw %}

##### output
{% raw %}
```html
<time data-available="false" datetime="2023-02-01">Feb 01, 23</time>
<time data-available="false" datetime="2023-02-02">Feb 02, 23</time>
<time data-available="false" datetime="2023-02-03">Feb 03, 23</time>
.
.
.
<time data-available="true" datetime="2023-02-27">Feb 27, 23</time>
<time data-available="false" datetime="2023-02-28">Feb 28, 23</time>
```
{% endraw %}

Inside the tag body, `result.days` is the list of [Availability Day]({% link docs/reference/objects/product/variant/accommodation_variant/availabilty_day.md %}) objects for each day in the computed range. With no extra parameters, that range is one month at a time (see `number_of_months`).


## Extra parameters

You can pass any of the following attributes on the tag. They are useful when building booking flows, calendars, or price checks for a specific window (for example, multi-step packages with fixed dates).

### start_date

Optional. First day of the range, inclusive. Accepts a date string (for example `"2024-04-15"`) or a Liquid variable that resolves to a string or `Date`.

When `start_date` is set, that exact calendar day is used as the start of the range (the range is **not** aligned to the start of the month). When omitted, the start of the range is the first day of the first month that has availability for the variant, as before.

If the value cannot be parsed as a date, it is ignored and the default behaviour applies.

##### syntax
{% raw %}
```liquid
{% accommodation_availability variant, start_date: "2024-04-15", end_date: "2024-04-20" %}
{% endaccommodation_availability %}

{% assign check_in = package_step.earliest_check_in_date %}
{% assign check_out = package_step.latest_check_out_date %}
{% accommodation_availability variant, start_date: check_in, end_date: check_out %}
{% endaccommodation_availability %}
```
{% endraw %}

### end_date

Optional. Last day of the range, inclusive. Same value types as `start_date`. The end of the range is **not** forced to the end of a month when `end_date` is provided.

When `start_date` is set but `end_date` is omitted, the end of the range is derived from `start_date` and `number_of_months`: from `start_date`, add `number_of_months - 1` months, then use the last day of that month (default `number_of_months` is `1`, so the range ends on the last day of `start_date`’s month).

When `end_date` is set but `start_date` is omitted, the start of the range is still the first month with availability for the variant (first day of that month), and the range runs through `end_date`.

If the value cannot be parsed as a date, it is ignored and the tag falls back to computing the end from `start_date` and `number_of_months`, or the default month-based range.

### number_of_months

Passing a number sets how many consecutive calendar months are spanned when **no** `end_date` is given. It defaults to `1` and can be a Liquid variable or a literal.

When both `start_date` and `end_date` are set, `number_of_months` does not change the end date. When only `start_date` is set, `number_of_months` controls how far forward the range extends, as described under `end_date`.

##### syntax
{% raw %}
```liquid
{% accommodation_availability variant, number_of_months: 2 %}
{% endaccommodation_availability %}
```
{% endraw %}
