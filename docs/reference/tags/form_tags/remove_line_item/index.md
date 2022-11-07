---
layout: default
title: Remove Line Item 
parent: Tags
grand_parent: Reference
has_children: false
---

The Remove Line Item Form Tag renders a button to remove an item from a cart.
The tag can be used with a single line item or when iterating over a collection of items. 

##### input
{% raw %}
```liquid
{% form 'remove_line_item' %}
   <input name="items[]" value="{{item.id}}" type="hidden" />
   <input type="submit" value="Remove" />
{% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/sites/line-items" accept-charset="UTF-8" method="post"><input type="hidden" name="_method" value="delete" autocomplete="off">
    <input name="items[]" value="1354af560050dec9a1611f7ac473d2e4" type="hidden">
    <input type="submit" value="Remove">
</form>
```
{% endraw %}

##### item ID
The HTML input tag requires the id of the item it is intended to remove.