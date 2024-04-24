---
layout: default
title: Package Booking
parent: Objects
---

# Package Booking
{: .d-inline-block }
object
{: .label .fs-1 }

Provides information about a customer's choices made while booking a [package]({% link docs/reference/objects/package.md %}).

<br>

#### Attributes

## `package_booking.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique id of the package booking.

## `package_booking.package`
{: .d-inline-block }
[Package]({% link docs/reference/objects/package.md %}).
{: .label .fs-1 }

The package that the customer is booking.

## `package_booking.adult_count`
{: .d-inline-block }
number
{: .label .fs-1 }

The number of guests that the customer is booking the package for.

## `package_booking.selected_start_date`
{: .d-inline-block }
Date
{: .label .fs-1 }

The customer's chosen date for the package.

It will return `nil` if the customer hasn't chosen a date.

## `package_booking.selected_start_time`
{: .d-inline-block }
string
{: .label .fs-1 }

The customer's chosen time for the package. Formatted as "HH:MM", in 24-hour clock time, e.g. "09:30".

It will return `nil` if the customer hasn't chosen a time.
