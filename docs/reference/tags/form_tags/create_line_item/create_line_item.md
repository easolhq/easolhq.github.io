---
layout: default
title: Create Line Item
parent: Tags
has_children: false
---

The Create Line Item Tag renders a form which acts as a wrapper for a single item.
Extra HTML input tags can be used to add item quantity, modifiers or adult count for per-unit items

##### input
{% raw %}
```liquid
    {% form "create_line_item" %}
        <input type="hidden" name="items[][variant_id]" value="{{item_id}}"/>
    {% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/sites/line-items" accept-charset="UTF-8" method="post">
    <input type="hidden" name="return_to" id="return_to" value="/admin/site_builder/sites/c94b650e/previews/book-tickets" autocomplete="off">
    <input type="hidden" name="items[][variant_id]" value="BAh7CEkiCGdpZAY6Bk....">
</form>
```
{% endraw %}

##### HTML Input
The HTML input requires `type="hidden"` and `value="item_id"`

##### Extra HTML input tags

Specify quantity
{% raw %}
```html
  <input type="hidden" name="items[][quantity]" value="**<quantity>**" />
```
{% endraw %}

Include a modifier
{% raw %}
```html
  <input type="hidden" name="items[][modifier_ids][]" value="**<modifier id>**" />
```
{% endraw %}

Specify adult count for a per-unit item
{% raw %}
```html
  <input type="hidden" name="items[][adult_count]" value="**<adult count>**" />
```
{% endraw %}


##### Extra Params
* `return_to:` To specify the redirect location, pass a URL as the value of the return_to: param.
The following example redirects to the homepage. 

##### input
{% raw %}
```liquid
{% form "create_line_item", return_to: '/home' %}
      <input type="hidden" data-variant-id="{{item_id}}" name="items[][variant_id]" value="{{item_id}}"/>
 {% endform %}
```
{% endraw %}