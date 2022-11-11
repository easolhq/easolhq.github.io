---
layout: default
title: Schedule Element
parent: Product
grand_parent: Objects
---

When using a `Schedule element` object you have access to the following attributes

# element.body

Returns the body of the host, this is a rich text field and so will return html as in the example above.

# element.heading

Returns the heading for the schedule element

# element.id

Returns a unique id for the schedule element

# element.image

Returns the [image]({% link docs/reference/objects/image.md %}) for the schedule element if present

# element.type

Schedule elements can be one of two types `title` or `section` , a title will only have the heading set whereas a section could have all attributes set. 

# element.included

Returns an `Array` of `Strings`  with what's included on this schedule element.

# element.not_included

Returns an `Array` of `Strings`  with what's not included on this schedule element.

# element.locale

Returns the locale for the schedule element

