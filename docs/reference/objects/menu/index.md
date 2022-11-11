---
layout: default
title: Menu
parent: Objects
has_children: true
has_toc: false
---

# Menu
{: .d-inline-block }
object
{: .label .fs-1 }

Menu templates define their own schema, in a similar way to blocks. All of the attributes defined on a menu's schema are made available via the `Menu` object.

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

Within the menu template, `menu.fixed` and `menu.background_colour` will be available. In this scenario, `menu.fixed` will return a boolean and `menu.background_colour` will return a [Color]({% link docs/reference/objects/color.md %}) object.

As well as the attributes that are available from the schema, the `Menu` object has the following attributes:

<br>

#### Attributes

## `menu.items`
{: .d-inline-block }
array of [menu item]({% link docs/reference/objects/menu/menu_item.md %})s
{: .label .fs-1 }

An array of the [menu items]({% link docs/reference/objects/menu/menu_item.md %})
