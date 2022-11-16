---
layout: default
title: Currency switcher
parent: Pricing & payments
---

# Currency switcher

For quick reference please see [Currency Switcher Tag]({% link docs/reference/tags/currency_switcher_tag/index.md %}).

A Creator sets all their prices in their own currency. However, their customers can see and buy in any preferred currency, amongst Easol's growing list of supported currencies.

When a customer lands on an Easol site page, we decide which currency should be used;
1. If the customer has been on the site before, the last currency they saw may still be stored in their cookies. Assuming the currency in the cookie is still a supported Easol currency, this is selected.
2. If no cookie is present (or it's not a supported currency) the currency is determined from the ip address that the page request came from. 
3. Finally, if a supported currency cannot be determined, the default Easol currency is used (currently USD $).

The page can now load. Any displayed prices will have their currency symbol and value based on the selected currency i.e. an exchange rate may be applied. Our exchange rates are updated frequently but not 'as if live'.
If the customer changes the currency using any currency switcher included on the page, the new currency is set to cookies and the page is re-rendered. 

Because of the above process we strongly recommend:
- At least one currency switcher should be present on any page with displayed prices. We include this in the footer template of all Easol Themes.
- No prices should ever be hardcoded or undergo calculations which use magic numbers.
