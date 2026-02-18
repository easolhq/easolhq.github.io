---
layout: default
title: Seat Group
parent: Objects
---

# Seat Group
{: .d-inline-block }
object
{: .label .fs-1 }

A group of seats in the same section and row, providing formatted display strings. These are retrieved from a [Cart Item]({% link docs/reference/objects/cart/cart_item.md %}).

#### Attributes

## `seat_group.description`
{: .d-inline-block }
string
{: .label .fs-1 }

The full description including section, row, and seat numbers, e.g. "Arena: Row A, Seats 1-3"

## `seat_group.location`
{: .d-inline-block }
string
{: .label .fs-1 }

The section and row without seat numbers, e.g. "Arena: Row A"

## `seat_group.seat_numbers_short`
{: .d-inline-block }
string
{: .label .fs-1 }

Just the seat numbers, e.g. "1-3" or "1, 3, 5"

## `seat_group.seat_numbers_long`
{: .d-inline-block }
string
{: .label .fs-1 }

The seat numbers with a prefix, e.g. "Seats 1-3" or "Seat 1"
