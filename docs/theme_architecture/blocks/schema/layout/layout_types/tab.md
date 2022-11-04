---
layout: default
title: Tab
parent: Layout types
nav_order: 1
---

# Tab
A layout `tab` groups variables in tabs in the Easol site builder. A `tab` can only be declared on the top level of a layout. 

## Attributes
A `tab` expects the following attributes:

#### type
`tab`

#### label
Defines the label for the tab shown to the Creator in the site builder. Accepts a string and must be a unique value.

#### elements
The attributes to be included within the tab. [Accordion toggles]({% link docs/guides/theme_architecture/blocks/schema/layout/layout_types/accordion_toggle.md %}) and [accordions]({% link docs/guides/theme_architecture/blocks/schema/layout/layout_types/accordion.md %}) can be nested within `tabs`.

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
layout:
    - type: tab
      label: Content
      elements: 
        - heading
        - text
---
```
{% endraw %}