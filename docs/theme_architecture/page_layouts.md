---
layout: default
title: Page layouts
parent: Theme architecture
---

# Page layouts

Page Layouts are predefined collections of blocks to help Creators quickly get going with a sensible layout. Each layout is defined in its own json file in the /pages folder of your theme and should have:
- a name
- a category 
- a collection of blocks 

## Name 
The page name is shown when choosing a page and also determines the name and slug of the page that is created. As slugs must be unique, if the slug is already in use it will be suffixed with a number (or the next available number), however, sites can have pages with the same name.

## Category 
The page category is used to group your page layouts, making it easier for Creators to browse and choose appropriate layouts. Categories will be shown in alphabetical order.

## Blocks 
Blocks will be included in the page based on the order they are included in the page layout definition. From just the block's key, the block will use all the default attributes associated with that block. However, you can override these defaults by assigning values to the attributes in the page layout definition. When a Creator is selecting a page layout, they will see a preview of the layout page including the attribute overrides.

e.g. For a file `my-theme/pages/name_of_page.json`
```
{
  "name": "Name of Page",
  "category": "Category",
  "blocks": [
    {
      "key": "hero_block",
      "attributes": {
        "block_attribute_1": "My amazing page",
        "block_attribute_2": false
      }
    },
    {
      "key": "text_block",
      "attributes": {
        "color": { "palette": "body-bg" }
      }
    },
    {
      "key": "video_block"
    }
  ]
}
```
