---
layout: default
title: Variables
parent: Schema
has_children: true
nav_order: 1
---

# Variables

Variables define the fields a Creator is able to use to customise the content and layout of a block. Variables are defined within the blocks using YAML front matter.

Variables consist of a `key`, which is used to access the variable within the block liquid code, and attributes which define the variable.

##### Example
{% raw %}
```
---
heading:
    type: string
    label: Block Heading
    group: content
text:
    type: text
    default: Enter some nice copy about your experience
image:
    type: image
    default:
        asset: images/sky.png
    label: Background Image
    group: design
    hint: Reccommended image size 1920px by 600px
---
```
{% endraw %}

## Common attributes
All variable types accept the following attributes:

#### Type
Defines the [type]({% link docs/guides/theme_architecture/blocks/schema/variables/variable_types/index.md %}) of the variable.

#### Label
Defines the label for the variable shown to the Creator in the site builder. Accepts a string. If no label is defined the variable key will be used.

#### Default
Defines a default value to be shown within the block preview. The variable will be prefilled with the default value when a Creator adds the block to a page. Accepted defaults depend on the variable [type]({% link docs/guides/theme_architecture/blocks/schema/variables/variable_types/index.md %}).

#### Group
Defines which tab the variable will be added to in site builder. Accepted groups are `content`, `layout`, `design` and `mobile`. 
If no group is defined the variable will be added to the `content` tab.
If a [layout]({% link docs/guides/theme_architecture/blocks/schema/layout/index.md %}) is defined in the block schema this will replace the default tabs and any defined `group`s will be ignored.

#### Hint
Defines additional copy to be included with a variable to provide additional context or guidance to Creators. Accepts markdown text.

#### Array
Defines whether a single variable is rendered, or if the Creator can add multiple instances of a variable. Accepts `true` or `false`. Multiple defaults can be defined on an array variable.

##### Syntax
{% raw %}
```
---
gallery:
    type: image
    array: true
    default:
        - asset: images/sky.png
        - asset: images/sky.png
---

{% for image in gallery %}
    <img src="{{image.url}}"> 
{% endfor %}
```
{% endraw %}

The length of the array can be checked by using the [size](https://shopify.dev/api/liquid/filters/array-filters#size) method.