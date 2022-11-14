---
layout: default
title: Layout
parent: Schema
has_children: true
nav_order: 2
---

# Layout

A block schema can include an optional `layout` section, which defines how the [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) are displayed to the Creator within the Easol site builder. When including a `layout`, block [variables]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) must be declared as attributes within the block schema.
<br><br>
[Layout types]({% link docs/theme_architecture/blocks/schema/layout/layout_types/index.md %}) can be nested in order to organise block variables further.
<br><br>
> Note: If a layout is defined this will replace the default site builder tabs and any [groups]({% link docs/theme_architecture/blocks/schema/variables/index.md %}) defined for variables will be ignored. Any variable not included in the layout will not be accessible in the block's Creator facing settings.

##### Example
{% raw %}
```
---
attributes:
    heading:
        type: string
        label: Block Heading
    text:
        type: text
        default: Enter some nice copy about your experience
    image:
        type: image
        default:
            asset: images/sky.png
        label: Background Image
        hint: Recommended image size 1920px by 600px
    cta_enabled:
        type: boolean
        label: Display a button
        default: true
    button_text:
        type: string
        default: Click me
        label: Button text
    button_link:
        type: link
        label: Button link
layout:
    - type: tab
      label: Content
      elements: 
        - type: accordion
          label: Text
          elements:
            - heading
            - text
        - type: accordion_toggle
          toggle_attribute: cta_enabled
          elements:
            - button_text
            - button_link
    - type: tab
      label: Design
      elements:
        - image
---
```
{% endraw %}