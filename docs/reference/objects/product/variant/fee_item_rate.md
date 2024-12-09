---
layout: default
title: Fee Item Rate
parent: Variant
grand_parent: Product
---

# Fee item rate
{: .d-inline-block }
object
{: .label .fs-1 }

Represents an instance of a fee being applied to a variant. For example, if
there's a cleaning fee of $50 applied to a variant and a booking fee of 5%,
there would be two fee item rates against the variant representing each fee.

#### Attributes

## `fee_item_rate.applies`
{: .d-inline-block }
string
{: .label .fs-1 }

A string representing the way this fee applies to the variant based on it's
guest and duration application strategies. This will be one of the following.

- Per item, per stay
- Per item, per night
- Per guest, per stay
- Per guest, per night

## `fee_item_rate.description`
{: .d-inline-block }
string
{: .label .fs-1 }

A description of the fee item rate.

If the fee is an amount, this will be the amount of the fee in the current
currency of the cart. If no currency is available this will return the amount
in the creator's home currency. This amount will be formatted as a string with
the currency symbol, e.g. "$10.00".

If the fee is a percentage, this will be a formatted string of the percentage
of the fee, e.g. "20%".

## `fee_item_rate.off_platform`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether or not this fee is a fee collected off of the Easol platform.

## `fee_item_rate.fee_name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the fee being applied, e.g. "Cleaning fee" or "Booking fee".
