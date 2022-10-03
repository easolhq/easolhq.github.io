---
layout: default
title: Accommodation Availability
parent: Tags
has_children: false
---

The Accommodation Availability Tag returns an array with [AvailabilityDayDrop's]({% link docs/reference/objects/product/variant/accommodation_variant/availabilty_day.md %}) for
all days in the first available month of the specified [variant]({% link docs/reference/objects/product/variant/accommodation_variant/index.md %}).

##### input
{% raw %}
```liquid
{% accommodation_availability variant %}
  {% for day in result.days %}
       <time data-available="{{day.available}}" datetime="{{day.date}}">{{day.date | date:"%b %d, %y"}}</time>
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
<time data-available="true" datetime="2023-02-04">Feb 04, 23</time>
<time data-available="true" datetime="2023-02-05">Feb 05, 23</time>
.
.
.
<time data-available="true" datetime="2023-02-27">Feb 27, 23</time>
<time data-available="false" datetime="2023-02-28">Feb 28, 23</time>
```
{% endraw %}

The tag returns a `days` array to the block passed in, the `days` array represents all days of the month for the first available month. It defaults to 1 month at a time.


# Extra Params

## Passing explicit attributes

It's possible to use any of the following attributes in the accommodation availability tag itself, this is useful for building a page responsible for a specific type of product:
* `number_of_months` Passing a number will result on the number of consecutive months that will be fetched. This defaults to 1.
