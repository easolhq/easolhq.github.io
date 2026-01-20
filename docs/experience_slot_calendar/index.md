---
layout: default
title: Experience slot calendar
has_children: true
nav_order: 8
has_toc: false
---

# Experience slot calendar

The `experience_slot_calendar` provides a way to render a calendar month with information about what experience slots are available on each date. The tag is scoped to one or more experiences.

The tag makes a [calendar]({% link docs/reference/objects/calendar.md %}) object available, which contains an array of [dates]({% link docs/reference/objects/experience_slot_calendar/date.md %}). Each `date` has information about the experience slots that are available on the date, such as `date.slot_count`, `date.sold_out`, `date.display_price` and `date.slots_by_variant`.

The [calendar]({% link docs/reference/objects/calendar.md %}) object also includes information about the current, next and previous months. Combining this with the use of the [search]({% link docs/reference/objects/search_query.md %}) object, it is possible to build a calendar UI that allows a user to navigate between months. See the example in [Navigatable calendar UI]({% link docs/experience_slot_calendar/index.md %}#navigatable-calendar-ui) for how this is possible.

The [date]({% link docs/reference/objects/experience_slot_calendar/date.md %}) object will ignore variants that have been hidden on specific experience slots.

> Note: Unlike the [product_search]({% link docs/product_search/index.md %}) and [experience_slot_search]({% link docs/experience_slot_search/index.md %}), parameters passed through query params will not be used automatically by the `experience_slot_calendar` calendar. Any parameters need to be explicitly passed into the tag as arguments.

##### input
{% raw %}
```liquid
{% experience_slot_calendar experience: product, month: 2, year: 2024 %}
  <ul>
    {% for date in calendar.dates %}
      <li>
        {{ date.date | date: "%Y-%m-%d" }}
        {% if date.slot_count == 0 %}
          (no availability)
        {% elsif date.sold_out %}
          (sold out)
        {% else %}
           (from {{ date.display_price.fractional | money }})
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% endexperience_slot_calendar %}
```
{% endraw %}

##### output
{% raw %}
```html
  <ul>
    <li>2024-02-01 (from £18.00)</li>
    <li>2024-02-02 (from £18.00)</li>
    <li>2024-02-03 (from £18.00)</li>
    <li>2024-02-04 (sold out)</li>
    <li>2024-02-05 (sold out)</li>
    <li>2024-02-06 (sold out)</li>
    <li>2024-02-07 (sold out)</li>
    <li>2024-02-08 (sold out)</li>
    <li>2024-02-09 (sold out)</li>
    <li>2024-02-10 (from £5.00)</li>
    <li>2024-02-11 (from £5.00)</li>
    <li>2024-02-12 (from £5.00)</li>
    <li>2024-02-13 (from £5.00)</li>
    <li>2024-02-14 (no availability)</li>
    <li>2024-02-15 (no availability)</li>
    <li>2024-02-16 (no availability)</li>
    <li>2024-02-17 (no availability)</li>
    <li>2024-02-18 (no availability)</li>
    <li>2024-02-19 (from £18.00)</li>
    <li>2024-02-20 (from £18.00)</li>
    <li>2024-02-21 (from £18.00)</li>
    <li>2024-02-22 (from £18.00)</li>
    <li>2024-02-23 (from £18.00)</li>
    <li>2024-02-24 (from £18.00)</li>
    <li>2024-02-25 (from £18.00)</li>
    <li>2024-02-26 (from £18.00)</li>
    <li>2024-02-27 (from £18.00)</li>
    <li>2024-02-28 (from £18.00)</li>
    <li>2024-02-29 (from £18.00)</li>
  </ul>
```
{% endraw %}

## Parameters
- `experience` [required]
  - This can be a `ProductDrop`, a string of the product ID or an array containing a combination of either.
- `month`
  - The month as a number, e.g. `2` would represent February.
  - This argument is ignored if `year` is blank.
  - If this is blank, it will default the next month that contains available slots.
- `year`
  - The year as a number, e.g. `2023`.
  - This argument is ignored if `month` is blank.
  - If this is blank, it will default the year of the next month that contains available slots.

## Navigatable calendar UI

It is possible to send the `month` and `year` parameters in the URL via the `?search` query param and for these properties to be available via the `search` drop, e.g. `search.month` and `search.year`. For example, a URL might look like the following:

`https://my-easol-site.com/my-calendar-page?search[month]=2&search[year]=2023`

We can pass these properties directly into the tag as arguments. If the `month` or `year` arguments are blank, it will default to using the next month that contains available experience slots.

The [calendar]({% link docs/reference/objects/calendar.md %}) object also exposes the current, next and previous months, which allows building a navigatable calendar UI.

The `calendar.first_day` method returns the first day in the month as a date, which can be used to render the name of the month. The same can be done with the next and previous months, e.g. `{% raw %}{{ calendar.next.first_day | date: "%B %Y" }}{% endraw %}`.

##### syntax
{% raw %}
```
{% experience_slot_calendar experience: product, month: search.month, year: search.year %}
  <h5>{{ calendar.first_day | date: "%B %Y" }}</h5>

  <ul>
    {% for date in calendar.dates %}
      <li>
        {{ date.date | date: "%Y-%m-%d" }}
      </li>
    {% endfor %}
  </ul>

  <div>
    <a href="?search[month]={{calendar.prev.month}}&search[year]={{calendar.prev.year}}">
      {{ calendar.prev.first_day | date: "%B %Y" }}
    </a>
    <a href="?search[month]={{calendar.next.month}}&search[year]={{calendar.next.year}}">
      {{ calendar.next.first_day | date: "%B %Y" }}
    </a>
  </div>
{% endexperience_slot_calendar %}
```
{% endraw %}

## Experiences with multiple time slots per day

It is possible for experiences to have multiple time slots on the same day. The `date.slots_by_variant` method can be used to display price and stock information for variants on each specific time slot.

##### syntax
{% raw %}
```
{% experience_slot_calendar experience: product %}
  <ul>
    {% for date in calendar.dates %}
      <li>
        {{ date.date | date: "%Y-%m-%d" }}

        {% for slot_variant in date.slots_by_variant %}
          <details>
            <summary>{{ slot_variant.variant.name }}</summary>
            <ul>
              {% for slot in slot_variant.slots %}
              <li>
                {{ slot.start_time }} ({{ slot.price.fractional | money }})
                {% if slot.sold_out %}
                  sold out
                {% elsif slot.remaining_stock < 5 %}
                  only {{ slot.remaining_stock }} stock left
                {% endif %}
              </li>
              {% endfor %}
            </ul>
          </details>
        {% endfor %}
      </li>
    {% endfor %}
  </ul>
{% endexperience_slot_calendar %}
```
{% endraw %}
