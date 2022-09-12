---
layout: default
title: Menu
parent: Objects
has_children: true
---

Menu templates define their own schema, in a similar way to blocks. All of the attributes defined on a menu's schema are made available via the `menu` object.

For example, consider the following menu schema:

```
---
max_item_levels: 1
supports_open_new_tab: true
attributes:
  fixed:
    type: boolean
    label: Fixed when scrolling
    group: design
    default: false
  background_colour:
    type: color
    label: Background colour
    group: design
    default: { palette: body-bg }
---
```

Within the menu template, `menu.fixed` and `menu.background_colour` will be available. In this scenario, `menu.fixed` will return a boolean and `menu.background_colour` will return a [color]({% link docs/reference/objects/color.md %}) object.

As well as the attributes that are available from the schema, the `menu` object has the following attributes:

# menu.items

Returns an array of the [menu items]({% link docs/reference/objects/menu/menu_item.md %})
