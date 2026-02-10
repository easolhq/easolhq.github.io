---
layout: default
title: Company
parent: Objects
---

# Company
{: .d-inline-block }
object
{: .label .fs-1 }

Company is a _global_ object, meaning it will always be accessible on any Liquid template.

<br>

#### Attributes

## `company.authors`
{: .d-inline-block }
array of [Author]({% link docs/reference/objects/author.md %})s
{: .label .fs-1 }

An array of the company's [authors]({% link docs/reference/objects/author.md %}).

## `company.avatar_logo`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The company's logo as an [image]({% link docs/reference/objects/image.md %}). 
The logo is set within **Settings** > **Your Brand**.

## `company.biographies`
{: .d-inline-block }
array of [Content]({% link docs/reference/objects/content_library.md %})s
{: .label .fs-1 }

An array of the company's [biographies]({% link docs/reference/objects/content_library.md %}).

## `company.booking_fee_name`
{: .d-inline-block }
string
{: .label .fs-1 }

The custom booking fee name, which can be overridden.
To enable this feature, please reach out to our support team at support@easol.com.
The default booking fee name is 'Booking Fee'.

## `company.countries`
{: .d-inline-block }
array of strings
{: .label .fs-1 }

An array of the names of countries with products. e.g. `["Canada", "United Kingdom"]`

## `company.facebook_username`
{: .d-inline-block }
string
{: .label .fs-1 }

The Facebook username set within **My Site** > **Social**.

## `company.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The id of the company. String representation of [Uuid format](https://en.wikipedia.org/wiki/Universally_unique_identifier).

## `company.instagram_username`
{: .d-inline-block }
string
{: .label .fs-1 }

The Instagram username set within **My Site** > **Social**.

## `company.logo`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The company's wordmark logo as an [image]({% link docs/reference/objects/image.md %}). 
The logo is set within **Settings** > **Your Brand**.

## `company.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the company.

## `company.organisation`
{: .d-inline-block }
[Organisation]({% link docs/reference/objects/organisation.md %})
{: .label .fs-1 }

The company's [organisation]({% link docs/reference/objects/organisation.md %}).

Note: Not all companies have an organisation.

## `company.posts`
{: .d-inline-block }
array of [Blog post]({% link docs/reference/objects/blog_post.md %})s
{: .label .fs-1 }

An array of the company's published [blog posts]({% link docs/reference/objects/blog_post.md %}), ordered by the most recently published first.

## `company.products`
{: .d-inline-block }
array of [Product]({% link docs/reference/objects/product/index.md %})s
{: .label .fs-1 }

An array of the company's published [products]({% link docs/reference/objects/product/index.md %}) excluding any private products.
e.g.

{% raw %}
```liquid
{% for product in company.products %}
    {{ product.name }}
{% endfor %}
```
{% endraw %}

## `company.series`
{: .d-inline-block }
array of [Series]({% link docs/reference/objects/series.md %})
{: .label .fs-1 }

An array of all the company's [series]({% link docs/reference/objects/series.md %}).

## `company.subdomain`
{: .d-inline-block }
string
{: .label .fs-1 }

The subdomain of the company.

## `company.time_zone_identifier`
{: .d-inline-block }
string
{: .label .fs-1 }

The company's timezone identifier (e.g., `"America/New_York"`, `"Europe/Madrid"`, or `"UTC"`).

This is useful when working with dates stored with timezone offsets in site builder custom fields. When dates are selected in datepickers, they are stored with the company's timezone offset applied. Use this attribute along with `time_zone_offset` to correctly interpret and display dates in Liquid templates.

## `company.time_zone_offset`
{: .d-inline-block }
integer
{: .label .fs-1 }

The company's UTC offset in seconds, accounting for daylight saving time (DST).

This value changes throughout the year for timezones that observe DST. For example:
- Eastern Standard Time (EST): `-18000` seconds (UTC-5)
- Eastern Daylight Time (EDT): `-14400` seconds (UTC-4)
- Central European Time (CET): `3600` seconds (UTC+1)
- Central European Summer Time (CEST): `7200` seconds (UTC+2)
- UTC: `0` seconds

Use this along with `time_zone_identifier` when working with dates from site builder custom fields to ensure dates are displayed correctly, especially for companies in timezones behind GMT where dates might otherwise shift to the previous day.

## `company.twitter_username`
{: .d-inline-block }
string
{: .label .fs-1 }

The Twitter username set within **My Site** > **Social**.
