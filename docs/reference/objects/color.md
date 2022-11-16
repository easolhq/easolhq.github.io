---
layout: default
title: Color
parent: Objects
---

# Color
{: .d-inline-block }
object
{: .label .fs-1 }

#### Attributes

## `color.alpha`
{: .d-inline-block }
number
{: .label .fs-1 }

The alpha component of the colour; a decimal number between 0.0 and 1.0.

## `color.blue`
{: .d-inline-block }
number
{: .label .fs-1 }

The blue component of the colour; a number between 0 and 255.

## `color.green`
{: .d-inline-block }
number
{: .label .fs-1 }

The green component of the colour; a number between 0 and 255.

## `color.hex`
{: .d-inline-block }
string
{: .label .fs-1 }

The Hex value of the colour. e.g. `#005ce6`

> When possible, use `color.rgba` over `color.hex`. The site builder's colour picker allows Creators to select an opacity; RGBA values in CSS will include a colour's opacity, whereas Hex values will ignore it.

## `color.red`
{: .d-inline-block }
number
{: .label .fs-1 }

The red component of the colour; a number between 0 and 255.

## `color.rgba`
{: .d-inline-block }
string
{: .label .fs-1 }

The RGBA value of the colour that can be used directly in CSS. e.g. `rgba(187, 207, 207, 1)`
