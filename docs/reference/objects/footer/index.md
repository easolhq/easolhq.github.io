---
layout: default
title: Footer
parent: Objects
has_children: true
---

Footer templates define their own schema, in a similar way to blocks. All of the attributes defined on a footer's schema are made available via the `footer` object.

For example, consider the following footer schema:

```
---
max_item_levels: 1
supports_open_new_tab: true
attributes:
  image:
    type: image
    label: Image
    group: design
  background_colour:
    label: Background colour
    type: color
    default: { palette: body-bg }
    group: design
---
```

Within the footer template, `footer.image` and `footer.background_colour` will be available. In this scenario, `footer.image` will return an [image]({% link docs/reference/objects/image.md %}) object and `footer.background_colour` will return a [color]({% link docs/reference/objects/color.md %}) object.

As well as the attributes that are available from the schema, the `footer` object has the following attributes:

# footer.items

Returns an array of the [footer items]({% link docs/reference/objects/footer/footer_item.md %})
