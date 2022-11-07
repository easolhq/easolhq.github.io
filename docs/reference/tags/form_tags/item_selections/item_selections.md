---
layout: default
title: Item Selections
parent: Tags
grand_parent: Reference
has_children: false
---

The Item Selections Tag returns an object which can be used as a wrapper to display modifiers for a given item.


##### input
{% raw %}
```liquid
    {% form 'item_selections', item %}
    {% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form action="/items/example/path/selections" accept-charset="UTF-8" method="post">
    <input type="hidden" name="_method" value="put" autocomplete="off">
    <input type="submit" id="save" value="Confirm my selections" disabled="">
</form>
```
{% endraw %}

##### Item param
The item param is required

##### Extra Params
* `guest::` A guest ID is required when the modifiers has a guest