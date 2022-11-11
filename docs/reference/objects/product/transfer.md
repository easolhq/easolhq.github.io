---
layout: default
title: Transfer
parent: Product
grand_parent: Objects
---

# Transfer
{: .d-inline-block }
object
{: .label .fs-1 }
deprecated
{: .label .fs-1 .label-red .ml-0 .mt-0 }

#### Attributes

## `transfer.departs_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date this transfer departs as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

## `transfer.arrives_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date this transfer arrives as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

## `transfer.return_departs_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date this transfer departs on the return leg of the journey, as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

## `transfer.return_arrives_on`
{: .d-inline-block }
timestamp
{: .label .fs-1 }

The date this transfer arrives on the return leg of the journey, as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

## `transfer.departure`
{: .d-inline-block }
string
{: .label .fs-1 }

A string of the date for the departure leg of the journey for this transfer. e.g. `"20 December 2023"`

## `transfer.return`
{: .d-inline-block }
string
{: .label .fs-1 }

A string of the date for the return leg of the journey for this transfer. e.g. `"27 December 2023"`
