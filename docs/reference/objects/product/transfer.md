---
layout: default
title: Transfer
parent: Product
grand_parent: Objects
---

When using a `transfer` object you have access to the following attributes:

# transfer.departs_on

Returns the date this transfer departs as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

# transfer.arrives_on

Returns the date this transfer arrives as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

# transfer.return_departs_on

Returns the date this transfer departs on the return leg of the journey, as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

# transfer.return_arrives_on

Returns the date this transfer arrives on the return leg of the journey, as a timestamp. This can then be used in conjunction with Liquid's [ built-in filters ](https://shopify.github.io/liquid/filters/date/).

# transfer.departure

Returns a string of the date for the departure leg of the journey for this transfer. e.g. `"20 December 2023"`

# transfer.return

Returns a string of the date for the return leg of the journey for this transfer. e.g. `"27 December 2023"`
