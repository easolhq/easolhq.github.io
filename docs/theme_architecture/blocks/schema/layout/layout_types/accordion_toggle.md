---
layout: default
title: Accordion toggle
parent: Layout types
nav_order: 3
---

# Accordion toggle
A layout `accordion_toggle` groups variables within an accordion in the Easol site builder. The accordion state is controlled by a `boolean` variable and additional elements are shown or hidden depending on the value of the `boolean`. An `accordion_toggle` can be nested inside a `tab`, but not within another `accordion` or `accordion_toggle`. 

## Attributes
An `accordion_toggle` expects the following attributes:

#### type
`accordion_toggle`

#### toggle_attribute
Defines the `boolean` variable which controls the accordion. The label for the accordion is taken from the variable label.

#### elements
The attributes to be included within the accordion.

##### Example
{% raw %}
```
---
attributes:
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
        - type: accordion_toggle
          toggle_attribute: cta_enabled
          elements:
            - button_text
            - button_link
---
```
{% endraw %}