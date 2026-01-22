---
layout: default
title: Packages search and calendar
parent: Tags
grand_parent: Reference
---

# Packages search and calendar

The `packages_search_and_calendar` tag provides a calendar-based way to search for and display package availability.

**Key feature**: When a date is selected in calendar view, you can fetch available start times with aggregated availability and pricing information, allowing customers to drill down from date → start time → specific packages.

## Basic Usage

##### input
{% raw %}
```liquid
{% packages_search_and_calendar packages: package_array %}
  <div class="calendar">
    {% for date in calendar.dates %}
      <div class="day">
        {{ date.start_on | date: "%A, %b %d" }}
        {% if date.has_start_times and date.sold_out == false %}
          <a href="?search[departure_date][equal_to]={{ date.start_on }}">{{ date.start_on }}</a> <!--Clickable date, pass other search params as needed -->
        {% else %}
          <p>{{ date.start_on }}</p> <!--Disabled date-->
        {% endif %}
      </div>
    {% endfor %}
  </div>
{% endpackages_search_and_calendar %}
```
{% endraw %}

---

## Parameters

### packages

**Type:** Array of Packages, or Package IDs

The only required parameter. Limit the search to specific packages. You can pass an array of package objects, or an array of package IDs.

{% raw %}
```liquid
{% packages_search_and_calendar packages: package_array %}
```
{% endraw %}

### guest_count

**Type:** Integer

**Default:** Minimum guest count across included packages

The number of guests to check availability for. This affects both availability checking and pricing calculations.

{% raw %}
```liquid
{% packages_search_and_calendar guest_count: 4 %}
```
{% endraw %}

### month

**Type:** Integer (1-12)

The month to display in the calendar view. Used together with `year` to control which month is shown.

{% raw %}
```liquid
{% packages_search_and_calendar month: 6, year: 2025 %}
```
{% endraw %}

### year

**Type:** Integer

The year to display in the calendar view. Used together with `month` to control which month is shown.

{% raw %}
```liquid
{% packages_search_and_calendar month: 6, year: 2025 %}
```
{% endraw %}

### departure_date

**Type:** Object

Filter results to a specific departure date. Pass an object with an `equal_to` key containing a date in YYYY-MM-DD format. When set, `result.start_times` will only include start times for that specific date.

{% raw %}
```liquid
{% packages_search_and_calendar departure_date: departure_date_object %}
```
{% endraw %}

When using query params, pass the date as:
```
?search[departure_date][equal_to]=2025-06-15
```

### page_size

**Type:** Integer (max 100)

**Default:** 5

Number of start time results per page.

{% raw %}
```liquid
{% packages_search_and_calendar page_size: 20 %}
```
{% endraw %}

### exclude_sold_out_products

**Type:** Boolean

**Default:** false

When true, excludes packages that are sold out from the results.

{% raw %}
```liquid
{% packages_search_and_calendar exclude_sold_out_products: true %}
```
{% endraw %}

### include_organisation_packages

**Type:** Boolean

**Default:** false

When true, allows searching for packages belonging to any company in the current company's organisation.

{% raw %}
```liquid
{% packages_search_and_calendar include_organisation_packages: true %}
```
{% endraw %}

---

## Search Params

Search params can be handled in one of two ways:

### Passing explicit attributes

You can pass any of the parameters listed above directly as attributes in the tag itself. This is useful for building a page with specific search criteria.

{% raw %}
```liquid
{% packages_search_and_calendar
   packages: package_array,
   guest_count: 4,
   month: 6,
   year: 2025,
   exclude_sold_out_products: true,
   include_organisation_packages: true
%}
```
{% endraw %}

### As query params

It's also possible to pass search params as query params. This is useful when building dynamic search pages.

Any of the above parameters can be used as a query param and should all be namespaced to `search`.

For example:
```
/packages?search[guest_count]=4&search[month]=6&search[year]=2025&search[departure_date][equal_to]=2025-06-15
```

**Params passed through a query param will override any of those specified as an attribute.**

### Accessing the query params

Once the search has been executed, you can get a reference to the params and values using the `search` object, which exposes all of the params listed in the Parameters section.

{% raw %}
```liquid
{{ search.guest_count }}
{{ search.month }}
{{ search.year }}
{{ search.departure_date.equal_to }}
{{ search.exclude_sold_out_products }}
{{ search.include_organisation_packages }}
```
{% endraw %}

---

## Objects Exposed

### calendar

The [calendar]({% link docs/reference/objects/calendar.md %}) object contains information about the current calendar view and its dates.
---

### date object

Each date in `calendar.dates` represents one day with aggregated availability information across all matching packages.

#### date.start_on
{: .d-inline-block }
Date
{: .label .fs-1 }

The date in YYYY-MM-DD format.

#### date.has_start_times
{: .d-inline-block }
Boolean
{: .label .fs-1 }

Whether there are any packages starting on this date.

#### date.sold_out
{: .d-inline-block }
Boolean
{: .label .fs-1 }

Whether all packages across all start times on this date are sold out.

---

### result

The `result` object contains list view data with pagination.

#### result.start_times
{: .d-inline-block }
Array of start_time objects
{: .label .fs-1 }

Array of start time objects with availability and pricing. See [start_time object](#start_time-object) below.

---

### start_time object

Each start time represents a specific time slot with aggregated availability information across all matching packages.

#### start_time.time
{: .d-inline-block }
String (HH:MM)
{: .label .fs-1 }

The start time in HH:MM format.

#### start_time.date
{: .d-inline-block }
Date
{: .label .fs-1 }

The start date for this start time.

#### start_time.sold_out
{: .d-inline-block }
Boolean
{: .label .fs-1 }

Whether the packages on this start time are sold out.

#### start_time.price
{: .d-inline-block }
[price]({% link docs/reference/objects/product/price.md %})
{: .label .fs-1 }

The minimum price across available packages for the specified guest count.

#### start_time.starting_stock
{: .d-inline-block }
Integer or nil
{: .label .fs-1 }

The total initial stock across all packages. Returns nil if any package has infinite stock.

#### start_time.remaining_stock
{: .d-inline-block }
Integer or nil
{: .label .fs-1 }

The total remaining stock across all packages. Returns nil if any package has infinite stock.

---

### paginate

Standard pagination object for list view results.

---

### search

The [search]({% link docs/reference/objects/search_query.md %}) object provides access to current search parameters.

---

## Example

This example demonstrates using query params to control the calendar view and Turbo to load start times when a date is selected.

##### input
{% raw %}
```liquid

<turbo-frame id="package-availability">
  {% packages_search_and_calendar packages: package_array %}

    <nav class="month-navigation">
      <a href="?search[month]={{ calendar.prev.month }}&search[year]={{ calendar.prev.year }}&search[guest_count]={{ search.guest_count }}" aria-label="Navigate to previous month">
        ← {{ calendar.prev.first_day | date: "%B %Y" }}
      </a>
      <h2>{{ calendar.first_day | date: "%B %Y" }}</h2>
      <a href="?search[month]={{ calendar.next.month }}&search[year]={{ calendar.next.year }}&search[guest_count]={{ search.guest_count }}" aria-label="Navigate to next month">
        {{ calendar.next.first_day | date: "%B %Y" }} →
      </a>
    </nav>

    <div class="calendar-grid">
      {% for date in calendar.dates %}
        <div class="calendar-day {% unless date.has_start_times %}unavailable{% endunless %}">
          <span class="day-number">{{ date.start_on | date: "%d" }}</span>

          {% if date.has_start_times and date.sold_out == false %}
            <a href="?search[departure_date][equal_to]={{ date.start_on }}&search[guest_count]={{ search.guest_count }}" class="calendar-date-link">
              Select
            </a>
          {% elsif date.sold_out %}
            <span class="sold-out">Sold out</span>
          {% endif %}
        </div>
      {% endfor %}
    </div>

    <div class="start-times-results">
      {% if result.start_times %}
        <h3>Available Start Times for {{ search.departure_date.equal_to | date: "%A, %B %d, %Y" }}</h3>
        {% for start_time in result.start_times %}
          <div class="start-time-card">
            <strong>{{ start_time.time }}</strong>
            {% unless start_time.sold_out %}
              <span class="price">{{ start_time.price | money }}pp</span>
              <a href="/booking?date={{ start_time.date }}&start_time={{ start_time.time }}">Book Now</a>
            {% else %}
              <span class="sold-out">Sold out</span>
            {% endunless %}
          </div>
        {% endfor %}
      {% endif %}
    </div>
  {% endpackages_search_and_calendar %}
</turbo-frame>

{% render 'some-scripts-to-handle-turbo' %}
```
{% endraw %}

**How it works:**

1. The entire calendar is wrapped in a `<turbo-frame>` with a unique ID
2. Month navigation links update the `search[month]` and `search[year]` query params, which Turbo intercepts and updates the frame
3. When a date is clicked, the `search[departure_date][equal_to]` param is set, which returns the same page with `result.start_times` populated for that date
4. Turbo automatically updates only the content within the frame, creating a seamless user experience
