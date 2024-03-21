---
layout: default
title: Enquiry form
parent: Tags
grand_parent: Reference
---

# Enquiry form

The `enquiry_form` tag renders a form which represents an Enquiry form that the Creator has constructed in the Admin.
Each input and label can be generated with [Input and label tags]({% link docs/reference/tags/form_tags/enquiry_form/field/input_and_label_tags.md %}).
It requires an enquiry form parameter to be passed. In the below example that is `swim_enquiry_form`.

<br>

#### Attributes

## `form.id`
{: .d-inline-block }
string
{: .label .fs-1 }

The unique ID for the form.


## `form.fields`
{: .d-inline-block }
array of [Field]({% link docs/reference/tags/form_tags/enquiry_form/field/index.md %})s
{: .label .fs-1 }

An array of all the form's [Field]({% link docs/reference/tags/form_tags/enquiry_form/field/index.md %})s

<br>

## Example

##### input
{% raw %}
```liquid
  {% form "enquiry_form", swim_enquiry_form %}
    {% for field in form.fields %}
      {% label field %}
      {% input field %}
    {% endfor %}
    <input type="submit" value="Send" />
  {% endform %}
```
{% endraw %}

##### output
{% raw %}
```html
<form data-controller="form" data-action="submit->form#submit" data-form-action="enquiry_form" action="/sites/enquiries" accept-charset="UTF-8" method="post">
  <label for="enquiry_custom_field_values_attributes_0_entry_attributes_value">Can you swim?</label>
  <input type="hidden" name="enquiry[custom_field_values_attributes][0][custom_field_id]" value="3082fdff-c938...">
  <input type="hidden" name="enquiry[custom_field_values_attributes][0][entry_type]" value="CustomField::Value::Boolean">
  <input type="text" name="enquiry[custom_field_values_attributes][0][entry_attributes][value]" id="enquirycustom_field_values_attributes_0_entry_attributes_value">

  <label for="enquiry_custom_field_values_attributes_1_entry_attributes_value">Special requests</label>
  <input type="hidden" name="enquiry[custom_field_values_attributes][1][custom_field_id]" value="fc3ab6b1-083b...">
  <input type="hidden" name="enquiry[custom_field_values_attributes][1][entry_type]" value="CustomField::Value::Boolean">
  <input type="text" name="enquiry[custom_field_values_attributes][1][entry_attributes][value]" id="enquiry_custom_field_values_attributes_1_entry_attributes_value">

  <input type="hidden" name="enquiry[enquiry_form_id]" value="81fb7e7b-88fa...">
  <input type="submit" value="Send">
</form>
```
{% endraw %}

## Additional parameters

### return_to

The `enquiry_form` tag will reload the customer's current page by default on form submit.
To direct a customer to a different page you can pass a URL as the value of the `return_to:` param.

The following example would redirect to the homepage:

##### input
{% raw %}
```liquid
{% form "enquiry_form", swim_enquiry_form, return_to: '/' %}
  ...
{% endform %}
```
{% endraw %}
