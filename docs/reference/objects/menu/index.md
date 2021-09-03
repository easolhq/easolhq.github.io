---
layout: default
title: Menu
parent: Objects
has_children: true
---

Additional logos can be found within [Company]({% link docs/reference/objects/company.md %})

The `menu` object has the following attributes:

# menu.background_colour

Returns the background colour selected within My Site > Menu

# menu.text_colour

Returns the text colour selected within My Site > Menu

# menu.fixed

Returns true if the menu is toggled to 'Fixed when scrolling' 

# menu.cta_enabled

Returns true if 'Show CTA' is toggled on

# menu.cta_text

Returns the text for the CTA

# menu.cta_target

Returns the target url for the CTA

# menu.brand_override

Returns the brand override logo as an [image]({% link docs/reference/objects/image.md %}). 

# menu.items

Returns an array of the menu [items]({% link docs/reference/objects/menu/menu_item.md %})

