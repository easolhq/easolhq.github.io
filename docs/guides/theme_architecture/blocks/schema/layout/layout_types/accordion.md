---
layout: default
title: Accordion
parent: Layout types
nav_order: 2
---

# Accordion
A layout `accordion` groups variables within an accordion in the Easol site builder. An `accordion` can be nested inside a `tab`, but not within another `accordion` or `accordion_toggle`. 

## Attributes
An `accordion` expects the following attributes:

#### type
`accordion`

#### label
Defines the label for the accordion shown to the Creator in the site builder. Accepts a string.

#### elements
The attributes to be included within the accordion.

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
        - type: accordion
          label: Text
          elements:
            - heading
            - text
---
```
{% endraw %}