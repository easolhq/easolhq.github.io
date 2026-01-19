---
layout: default
title: Calendar
parent: Objects
---

# Calendar
{: .d-inline-block }
object
{: .label .fs-1 }

The calendar object used by [experience_slot_calendar]({% link docs/reference/tags/experience_slot_calendar_tag.md %}) tag

#### Attributes

## `calendar.dates`
{: .d-inline-block }
array of dates
{: .label .fs-1 }

The [experience slot dates]({% link docs/reference/objects/experience_slot_calendar/date.md %}) returned within this calendar month.

## `calendar.first_day`
{: .d-inline-block }
date
{: .label .fs-1 }

The first day in this calendar month. This can be used along with the Liquid's [date filter](https://shopify.github.io/liquid/filters/date/) filter to display the name of the month, e.g. `{% raw %}{{ calendar.next.first_day | date: "%B %Y" }}{% endraw %}`.

## `calendar.month`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of the calendar month.

## `calendar.next`
{: .d-inline-block }
object
{: .label .fs-1 }

An object representing the next calendar month, which includes the following methods:
- `first_day`
- `month`
- `year`

## `calendar.prev`
{: .d-inline-block }
object
{: .label .fs-1 }

An object representing the previous calendar month, which includes the following methods:
- `first_day`
- `month`
- `year`

## `calendar.year`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of the calendar year.
