---
layout: default
title: Create line item
parent: Tags
grand_parent: Reference
---

# Create line item

The `create_line_item` tag renders a form which acts as a wrapper for a single item, an item can be a [variant]({% link docs/reference/objects/product/variant/index.md %}) or an [extra]({% link docs/reference/objects/product/extra.md %}).<br>
Extra HTML input tags can be used to add item quantity, modifiers, adult count or start and end date.<br>
An [experience date]({% link docs/reference/objects/product/experience_date.md %}) can be referenced to book a specific date.

##### input
{% raw %}
```liquid
    {% form "create_line_item" %}
        <input type="hidden" name="items[][variant_id]" value="**<variant.id or extra.id>**"/>
    {% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/sites/line-items" data-form-action="create_line_item" accept-charset="UTF-8" method="post">
    <input type="hidden" name="return_to" id="return_to" value="/admin/site_builder/sites/c94b650e/previews/book-tickets" autocomplete="off">
    <input type="hidden" name="items[][variant_id]" value="BAh7CEkiCGdpZAY6Bk....">
</form>
```
{% endraw %}

## Extra HTML input tags

### Quantity

{% raw %}
```html
  <input type="hidden" name="items[][quantity]" value="**<quantity>**" />
```
{% endraw %}

### Modification

Include a modifier by referencing the [modifier.id]({% link docs/reference/objects/product/modifier.md %})
{% raw %}
```html
  <input type="hidden" name="items[][modifier_ids][]" value="**<modifier.id>**" />
```
{% endraw %}

### Adult count

Specify adult count for a per-unit item or accommodation
{% raw %}
```html
  <input type="hidden" name="items[][adult_count]" value="**<adult count>**" />
```
{% endraw %}

### Check-in/Check-out

Specify check-in and check-out dates for accommodation items
{% raw %}
```html
  <input type="hidden" name="items[][start_on]" value="**<YYYY-MM-DD>**">
  <input type="hidden" name="items[][end_on]" value="**<YYYY-MM-DD>**">
```
{% endraw %}

### Experience date

Specify the experience date to be booked for experience items by referencing the [experience_date.id]({% link docs/reference/objects/product/experience_date.md %}#experience_dateid).
{% raw %}
```html
  <input type="hidden" name="items[][experience_slot_id]" value="**<experience_date.id>**" />
```
{% endraw %}

### Clear cart

Clear all existing items out of a customer's cart before adding new items.
{% raw %}
```html
  <input type="hidden" name="clear_cart">
```
{% endraw %}

## Extra parameters

### return_to

The `create_line_item` tag will reload the customer's current page by default on form submit.
To direct a customer to a different page you can pass a URL as the value of the `return_to:` param.

The following example redirects to the homepage.

##### input
{% raw %}
```liquid
{% form "create_line_item", return_to: '/' %}
  <input type="hidden" name="items[][variant_id]" value="**<variant.id or extra.id>**"/>
{% endform %}
```
{% endraw %}
