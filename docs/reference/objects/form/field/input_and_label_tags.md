---
layout: default
title: Input and Label tags
parent: Field
---

# Form field tags
{: .d-inline-block }
object
{: .label .fs-1 }

The input and label tags can be used to render each [field]({% link docs/reference/objects/form/field/index.md %}) in an [Enquiry form]({% link docs/reference/tags/form_tags/enquiry_form/index.md %})

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

Extra parameters passed to the input or label tags will be rendered as attributes on the html elements.


##### input
{% raw %}
```liquid
{% input field, required: true, class: 'nice-input', data-bar: 'foo' %}
```
{% endraw %}

##### output
{% raw %}
```html
<input ... required="required" class="nice-input" data-bar="foo" >
```
{% endraw %}