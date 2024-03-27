---
layout: default
title: Form field
parent: Enquiry form
grand_parent: Tags
---

# Form field
{: .d-inline-block }
object
{: .label .fs-1 }

Represents each field of an Enquiry form that the Creator has constructed in the Admin.

<br>

#### Attributes

## `field.errors`
{: .d-inline-block }
array of strings
{: .label .fs-1 }

After a failed form submission, `errors` will return an array of error messages for any
validations that have failed for this field. These will all be lowercase.

E.g. `can't be blank`, `is invalid`.


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

## `field.type`
{: .d-inline-block }
string
{: .label .fs-1 }

Returns a string indicating the input type, e.g. `text` for a element type of `<input type="text">`.
