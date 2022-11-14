---
layout: default
title: Currency switcher
parent: Tags
grand_parent: Reference
has_children: false
---

# Currency switcher

The `currency_switcher` tag returns an HTML form with a drop-down menu of currency options. 
When a currency is selected, the form emits a submit event which updates the currency site-wide and reloads the page.

##### input
{% raw %}
```liquid
{% currency_switcher %}
```
{% endraw %}

##### output
{% raw %}
```html
<form class="currency-switcher" action="/set-currency" accept-charset="UTF-8" method="post">
<input type="hidden" name="authenticity_token" id="authenticity_token" value="csrf_token" autocomplete="off" />
    <select name="currency" id="currency" aria-label="Change currencies" onchange="this.form.submit()" class="form-control custom-select">
        <option value="AUD">A$ Australian Dollar</option>
        <option value="CAD">CAD$ Canadian Dollar</option>
        <option value="CHF">CHF Swiss Franc</option>
        <option value="EUR">€ Euro</option>
        <option value="GBP">£ British Pound</option>
        <option value="RON">Lei Romanian Leu</option>
        <option selected="selected" value="USD">$ United States Dollar</option>
        <option value="JPY">¥ Japanese Yen</option>
        <option value="ZAR">R South African Rand</option>
    </select>
</form>"
```
{% endraw %}
