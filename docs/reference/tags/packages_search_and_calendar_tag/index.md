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
        {% if date.available %}
          <a href="?search[date]={{ date.start_on }}">{{ date.start_on }}</a> <!--Clickable date-->
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

### start_date

**Type:** Date (YYYY-MM-DD format)

**Default:** Today's date

Start of the date range to search within. Used for both calendar and list views.

{% raw %}
```liquid
{% packages_search_and_calendar start_date: "2024-12-20" %}
```
{% endraw %}

### end_date

**Type:** Date (YYYY-MM-DD format)

**Default:** No end date limit

End of the date range to search within.

{% raw %}
```liquid
{% packages_search_and_calendar end_date: "2024-12-31" %}
```
{% endraw %}

### page_size

**Type:** Integer (max 100)

**Default:** 10

Number of results per page when using list view with `result.items`.

{% raw %}
```liquid
{% packages_search_and_calendar page_size: 20 %}
```
{% endraw %}

### exclude_sold_out

**Type:** Boolean

**Default:** false

When true, excludes packages that are sold out from the results.

{% raw %}
```liquid
{% packages_search_and_calendar exclude_sold_out: true %}
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
   start_date: "2024-12-20",
   exclude_sold_out: true
%}
```
{% endraw %}

### As query params

It's also possible to pass search params as query params. This is useful when building dynamic search pages.

Any of the above parameters can be used as a query param and should all be namespaced to `search`.

For example:
```
/packages?search[guest_count]=4&search[start_date]=2024-12-20&search[exclude_sold_out]=true
```

**Params passed through a query param will override any of those specified as an attribute.**

### Accessing the query params

Once the search has been executed, you can get a reference to the params and values using the `search` object, which exposes all of the params listed in the Parameters section.

{% raw %}
```liquid
{{ search.guest_count }}
{{ search.start_date }}
{{ search.exclude_sold_out }}
```
{% endraw %}

---

## Objects Exposed

### calendar

The `calendar` object contains information about the current calendar view and its dates.

#### calendar.dates
{: .d-inline-block }
Array of date objects
{: .label .fs-1 }

Array of date objects for the current view (week or month). See [date object](#date-object) below.

#### calendar.first_day
{: .d-inline-block }
Date
{: .label .fs-1 }

The first day in the current calendar view.

{% raw %}
```liquid
{{ calendar.first_day | date: "%B %Y" }}
<!-- Output: December 2024 -->
```
{% endraw %}

#### calendar.last_day
{: .d-inline-block }
Date
{: .label .fs-1 }

The last day in the current calendar view.

#### calendar.view_mode
{: .d-inline-block }
String
{: .label .fs-1 }

Returns `'week'` or `'month'` depending on the `calendar_view` parameter.

#### calendar.prev
{: .d-inline-block }
Object
{: .label .fs-1 }

Information about the previous calendar period. Contains:
- `calendar.prev.week` - Previous week number (when in week view)
- `calendar.prev.month` - Previous month number
- `calendar.prev.year` - Previous year
- `calendar.prev.first_day` - First day of previous period

#### calendar.next
{: .d-inline-block }
Object
{: .label .fs-1 }

Information about the next calendar period. Contains:
- `calendar.next.week` - Next week number (when in week view)
- `calendar.next.month` - Next month number
- `calendar.next.year` - Next year
- `calendar.next.first_day` - First day of next period

---

### date object

Each date in `calendar.dates` represents one day with aggregated availability information across all matching packages.

#### date.start_on
{: .d-inline-block }
Date
{: .label .fs-1 }

The date in YYYY-MM-DD format.

#### date.available
{: .d-inline-block }
Boolean
{: .label .fs-1 }

Whether any packages are available on this date.

#### date.start_times_url
{: .d-inline-block }
String
{: .label .fs-1 }

A pre-built URL endpoint that includes the date and current search parameters. This URL is designed to be used with Turbo (or AJAX) to fetch and display available start times when a user clicks on a date.

The URL automatically includes:
- The selected date (`date` parameter)
- Current search parameters (e.g., `guest_count`, `packages`)

See [Start Times Endpoint](#start-times-endpoint) below for implementation details.

---

### result

The `result` object contains list view data with pagination.

#### result.start_times
{: .d-inline-block }
Array of package result objects
{: .label .fs-1 }

Array of new drops with availability and pricing. Each item contains:

##### start_time.time
{: .d-inline-block }
String (HH:MM)
{: .label .fs-1 }

The start time for this package instance (if applicable).

##### start_time.date
{: .d-inline-block }
String (HH:MM)
{: .label .fs-1 }

The start date for this start time.

##### item.available
{: .d-inline-block }
Boolean
{: .label .fs-1 }

Whether this package instance is available for booking.

##### item.price
{: .d-inline-block }
Money object
{: .label .fs-1 }

Total price for the specified guest count.

##### item.price_per_person
{: .d-inline-block }
Money object
{: .label .fs-1 }

Per-person price.

---

### paginate

Standard pagination object for list view results.

---

### search

The [search]({% link docs/reference/objects/search_query.md %}) object provides access to current search parameters.

---

## Start Times Endpoint

When a date is clicked in calendar view, you can use `date.start_times_url` to fetch available start times for that specific date. This endpoint returns the same page template with the `result` object populated with start time details.

### How It Works

1. Each `date` in the calendar has a pre-built `start_times_url`
2. This URL includes the selected date and all current search parameters
3. When fetched (via Turbo or AJAX), it returns the page with `result.package_search_results` populated for that date
4. Use Turbo frames to reload only the start times section of your page

**URL Format:**
```
/package_start_times?date=2024-12-20&search[guest_count]=4&search[packages][]=pkg_123
```

**Response:**
The endpoint returns the same page template with `result.package_search_results` containing available start times for the selected date.

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
        <div class="calendar-day {% unless date.available %}unavailable{% endunless %}">
          <span class="day-number">{{ date.start_on | date: "%d" }}</span>

          {% if date.available %}
            <a href="{{ date.start_times_url }}" class="calendar-date-link">
              <span class="price">From {{ date.cheapest_price_per_person.fractional | money }}pp</span>
              {% if date.remaining_stock < 5 %}
                <span class="low-stock">{{ date.remaining_stock }} left</span>
              {% endif %}
            </a>
          {% elsif date.sold_out %}
            <span class="sold-out">Sold out</span>
          {% endif %}
        </div>
      {% endfor %}
    </div>

    <div class="start-times-results">
      {% if result.start_times %}
        <h3>Available Start Times for {{ search.date | date: "%A, %B %d, %Y" }}</h3>
        {% for start_time in result.start_times %}
          <div class="start-time-card">
            <strong>{{ start_time.time }}</strong>
            {% if start_time.available %}
              <span class="price">{{ start_time.price_per_person }}pp</span>
              <a href="/booking?package={{ start_time.package.id }}&start_time={{ start_time.time }}">Book Now</a>
            {% else %}
              <span class="sold-out">Sold out</span>
            {% endif %}
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
3. When a date is clicked, the `date.start_times_url` navigates to a URL that returns the same page with `result.start_times` populated for that date
4. Turbo automatically updates only the content within the frame, creating a seamless user experience
