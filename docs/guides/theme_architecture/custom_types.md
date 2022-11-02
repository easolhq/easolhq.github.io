---
layout: default
title: Custom types
parent: Theme architecture
nav_order: 8
---

# Custom types

Custom types allow you to define reusable objects which include multiple [variable]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) fields.
They are defined in a theme in the types directory as individual json files, which can then be refered to in any [block schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) using the custom type's `key`. 

## Custom type structure
All custom types expect the following key-value pairs:

#### Key
The custom type's unique key, used in the block schema to reference the custom type.

#### Name
The name of the custom type shown to the Creator in the site builder.

#### Attributes
An array of [variable]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) objects, defining the individual variable fields to be included in the custom type.


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
