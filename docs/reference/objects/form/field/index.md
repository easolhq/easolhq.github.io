---
layout: default
title: Field
parent: Form
---

# Form field
{: .d-inline-block }
object
{: .label .fs-1 }

Represents each field of an Enquiry form that the Creator has constructed in the Admin.

<br>

#### Attributes

## `field.hint`
{: .d-inline-block }
string
{: .label .fs-1 }

The hint is constructed in a WYSIWYG editor and is returned with HTML markup.


## `field.label`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the string that should be used as the input's label.


## `field.name`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns the string that should be set as the name attribute, to ensure successful form submission.


## `field.required`
{: .d-inline-block }
boolean
{: .label .fs-1 }

Returns `true` or `false` depending on whether the field is required for successful form submission.
