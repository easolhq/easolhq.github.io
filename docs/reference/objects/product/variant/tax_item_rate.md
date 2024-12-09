---
layout: default
title: Tax Item Rate
parent: Variant
grand_parent: Product
---

# Tax item rate
{: .d-inline-block }
object
{: .label .fs-1 }

Represents an instance of a tax being applied to a variant. For example, if 20%
VAT is applied a variant as well as a city tax of 5%, there would be two tax
item rates against the variant representing each tax.

#### Attributes

## `tax_item_rate.applies`
{: .d-inline-block }
string
{: .label .fs-1 }

A string representing the way this tax applies to the variant based on it's
guest and duration application strategies. This will be one of the following.

- Per item, per stay
- Per item, per night
- Per guest, per stay
- Per guest, per night

## `tax_item_rate.description`
{: .d-inline-block }
string
{: .label .fs-1 }

A description of the tax item rate.

If the tax is an amount, this will be the amount of the tax in the current
currency of the cart. If no currency is available this will return the amount
in the creator's home currency. This amount will be formatted as a string with
the currency symbol, e.g. "$10.00".

If the tax is a percentage, this will be a formatted string of the percentage
of the tax, e.g. "20%".

## `tax_item_rate.off_platform`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether or not this tax is a tax collected off of the Easol platform.

## `tax_item_rate.tax_name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the tax being applied, e.g. "VAT" or "New York State Tax".
