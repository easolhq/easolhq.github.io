---
layout: default
title: Package Product
parent: Package Step
---

# Package Product
{: .d-inline-block }
object
{: .label .fs-1 }

Represents a [product]({% link docs/reference/objects/product/index.md %}) that's been included in a [package]({% link docs/reference/objects/package.md %}), along with the subset of the [variants]({% link docs/reference/objects/product/variant/index.md %}) of that product that the creator specified to be bookable through the package.

<br>

#### Attributes

## `package_product.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique id of the package product.

## `package_product.product`
{: .d-inline-block }
[Product]({% link docs/reference/objects/product/index.md %})
{: .label .fs-1 }

The specific product that's associated to the Package Product.

## `package_product.variants`
{: .d-inline-block }
Array of [Variant]({% link docs/reference/objects/product/variant/index.md %})
{: .label .fs-1 }

The variants of the `package_product.product` that the creator has included in the package and are eligible for booking by the customer.

## `package_product.items`
{: .d-inline-block }
Array of [Package Step Item]({% link docs/reference/objects/package/step/item.md %})
{: .label .fs-1 }

An array of package step items for the `package_product.product`.
