---
layout: default
title: Package
parent: Objects
---

# Package
{: .d-inline-block }
object
{: .label .fs-1 }

The package object represents a package, which is a collection of items that can be purchased together.

<br>

#### Attributes

## `package.id`
{: .d-inline-block }
string
{: .label .fs-1 }
The unique id of the package.

## `package.name`
{: .d-inline-block }
string
{: .label .fs-1 }

The name of the package.

## `package.tagline`
{: .d-inline-block }
string
{: .label .fs-1 }

The tagline of the package.

## `package.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Will always return "`package`".

## `package.image`
{: .d-inline-block }
[Image]({% link docs/reference/objects/image.md %})
{: .label .fs-1 }

The package's image.

## `package.items`
{: .d-inline-block }
[Package Item]({% link docs/reference/objects/package/item.md %})
{: .label .fs-1 }

The included items in the package.

## `package.off_sale`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Whether the package is off sale.

## `package.off_sale_copy`
{: .d-inline-block }
string
{: .label .fs-1 }

The copy to display when the package is off sale.

## `package.state`
{: .d-inline-block }
string
{: .label .fs-1 }

The state of the package. Can be one of:
- draft
- selling
- off_sale







