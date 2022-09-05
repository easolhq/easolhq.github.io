---
layout: default
title: Color
parent: Objects
---

The `color` object has the following attributes. More information about how RGB and Hex colors are used in CSS can be seen here - [CSS Colors](https://www.w3schools.com/css/css_colors.asp).

# color.alpha

The alpha component of the color, which is a decimal number between 0.0 and 1.0.

# color.blue

The blue component of the color, which is a number between 0 and 255.

# color.green

The green component of the color, which is a number between 0 and 255.

# color.hex

The Hex value of the color. e.g. `#005ce6`

> When possible, prefer using `color.rgba` over `color.hex`. The site builder's color picker allows users to select an opacity. RGBA values in CSS will include a color's opacity, whereas Hex values will ignore it.

# color.red

The red component of the color, which is a number between 0 and 255.

# color.rgba

The RGBA value of the color as a string that can be used directly in CSS. e.g. `rgba(187, 207, 207, 1)`
