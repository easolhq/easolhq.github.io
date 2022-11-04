---
layout: default
title: Index.json
parent: Blocks
nav_order: 5
---

# Index.json

The `index.json` in the blocks folder defines which blocks are available to a theme and also the categories for these, used to group the blocks within the Easol site builder.

{% raw %}
```json
{
  "example": {
    "name": "Example block",
    "category": "Text"
  }
}
```
{% endraw %}

#### Name
The block name is shown when a Creator is choosing or editing a block.

#### Category
The block category is used to group blocks, making it easier for Creators to browse and choose appropriate blocks. Categories will be shown in alphabetical order.