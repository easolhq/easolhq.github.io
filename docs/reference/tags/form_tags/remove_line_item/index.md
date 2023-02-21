---
layout: default
title: Remove line item 
parent: Tags
grand_parent: Reference
---

# Remove line item

The `remove_line_item` tag renders a button to remove an item from a cart.
The tag can be used with a single line item or when iterating over a collection of items. 

##### input
{% raw %}
```liquid
{% form 'remove_line_item' %}
   <input name="items[]" value="**<variant.id or extra.id>**" type="hidden" />
   <input type="submit" value="Remove" />
{% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/sites/line-items" data-form-action="remove_line_item" accept-charset="UTF-8" method="post">
  <input type="hidden" name="_method" value="delete" autocomplete="off">
  <input name="items[]" value="1354af560050dec9a1611f7ac473d2e4" type="hidden">
  <input type="submit" value="Remove">
</form>
```
{% endraw %}

## Extra parameters

### return_to

The `remove_line_item` tag will reload the customer's current page by default on form submit.
To direct a customer to a different page you can pass a URL as the value of the `return_to:` param.

The following example redirects to the homepage.

##### input
{% raw %}
```
{% form 'remove_line_item', return_to: '/' %}
   <input name="items[]" value="**<variant.id or extra.id>**" type="hidden" />
   <input type="submit" value="Remove" />
{% endform %}
```
{% endraw %}