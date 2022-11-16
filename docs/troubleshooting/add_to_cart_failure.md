---
layout: default
title: Item not added to cart
parent: Troubleshooting
---

## Items are not added to a customer's cart when submitting a create_line_item form

For quick reference, see [create_line_item]({% link docs/carts/cart_interactions/add_line_items.md %})

When adding an item to a cart, all relevant information needs to be included in the form to ensure the item is added successfully. The information required depends on the configuration of the experience.

If your form is failing to add items to a customer's cart, below are some initial troubleshooting steps.

- Which product shape is failing to add to the cart? Is it all experiences and accommodations, or just a subset?
- Are all required input fields included? If only some experiences or accommodations are failing to be added to the cart, are there some fields missing?
- Do the failing items have modifier groups assigned to them, and if so, have these been included in the form?
- Is the item sold out or is the specified modification option sold out? If so, add support to display items as [sold out]({% link docs/reference/objects/product/index.md %}#productsold_out) and hide the add to cart form.


### Breakdown of form fields

| Field         | Required on                                   |
|:--------------|:----------------------------------------------|
| variant_id    | All variants                                  |
| quantity      | All variants                                  |
| modifier_ids  | All variants with modifications               |
| adult_count   | All accommodation variants, per unit variants |
| start_on      | All accommodation variants                    |
| end_on        | All accommodation variants                    |