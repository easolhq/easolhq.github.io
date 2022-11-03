---
layout: default
title: Header
parent: Site Navigation
nav_order: 1
---

The main site navigation can be managed by Creators in **My Site > Header** or any site page. It's contents and results can be edited in the menu template. Please note that the terms "Header" and "Menu" might be used interchangeably.

## Menu template
The [menu] is a particular kind of [partial]({% link docs/guides/theme_architecture/partials/index.md %}) which is rendered in all site pages, always at the start of the `body` tag. It contains a [schema]({% link docs/guides/theme_architecture/blocks/schema/index.md %}) where [variables]({% link docs/guides/theme_architecture/blocks/schema/variables/index.md %}) can be edited. The site navigation and all it's attributes can be accessed through the [menu]({% link docs/reference/objects/menu/index.md %}) object. Refer to it for a full reference and examples.