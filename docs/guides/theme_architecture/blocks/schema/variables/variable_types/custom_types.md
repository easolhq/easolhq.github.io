---
layout: default
title: Custom types
parent: Variable types
grand_parent: Variables
---

# Custom types

Custom types allow you to define reusable objects which include multiple variable fields.
They are defined in a theme in the [/types]({% link docs/guides/theme_architecture/custom_types.md %}) directory as a json file, which can then be refered to in any block using the custom type `key`. Custom types return an object.

##### Example custom type defined in the [/types]({% link docs/guides/theme_architecture/custom_types.md %}) directory
{% raw %}
```json
{
  "key": "my_custom_type",
  "name": "My custom type",
  "attributes": [
    {
      "name": "label",
      "type": "string"
    },
	{
      "name": "link",
      "type": "link"
    },
    {
      "name": "style",
      "type": "select",
      "options": [
        {
          "label": "primary",
          "value": "btn-primary"
        },
        {
          "label": "secondary",
          "value": "btn-secondary"
        }
      ]
    }
  ]
}
```
{% endraw %}

##### Example custom type used in block schema
{% raw %}
```
---
my_variable:
    type: my_custom_type
---

<a class="{{my_variable.style}}" href="{{my_variable.link.url}}">{{my_variable.label}}</a>
```
{% endraw %}

## Setting defaults
Defaults can be set on custom types as a key, value pair. Any defaults set within the block schema will overide the defaults set in the [custom type json file]({% link docs/guides/theme_architecture/custom_types.md %}).

##### syntax
{% raw %}
```
---
my_variable:
    type: my_custom_type
    default:
        label: Click here
        style: btn-primary
---

<a class="{{my_variable.style}}" href="{{my_variable.link.url}}">{{my_variable.label}}</a>
```
{% endraw %}

## Arrays
You can also define arrays of custom types to build more complex UI’s, for example to allow a Creator to add an array of buttons.

##### syntax
{% raw %}
```
---
buttons:
    type: my_custom_type
    array: true
    default:
        - label: Click here
          style: btn-primary
        - label: Click here
          style: btn-secondary
---
{% for button in buttons %}
    <a class="{{button.style}}" href="{{button.link.url}}">{{button.label}}</a>
{% endfor %}    
```
{% endraw %}