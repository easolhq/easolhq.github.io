---
layout: default
title: Custom types
parent: Theme architecture
nav_order: 8
---

# Custom types

Custom types allow you to define reusable objects which include multiple [variable]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) fields.
They are defined in a theme in the types directory as individual json files, which can then be referred to in any [block schema]({% link docs/theme_architecture/blocks/schema/index.md %}) using the custom type's `key`. 

## Custom type structure
All custom types expect the following key-value pairs:

#### Key
The custom type's unique key, used in the block schema to reference the custom type.

#### Name
The name of the custom type shown to the Creator in the site builder.

#### Attributes
An array of [Variable]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) objects, defining the individual variable fields to be included in the custom type.


##### e.g. For a file my-theme/types/my_custom_type.json
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

## Updating custom types
After a custom type has been created, existing attributes cannot be removed and an attribute's `name` and `type` cannot be changed. Additional attributes can be added to existing custom types.

## Deleting custom types
A custom type can only be deleted if it is not referenced in any theme [blocks]({% link docs/theme_architecture/blocks/index.md %}) or blocks added to Creator websites.

The above restrictions are in place to ensure that changes are not made to custom types on which existing blocks depend.