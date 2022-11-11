---
layout: default
title: Site Styles
has_children: true
nav_order: 3
---

**My Site > Style** is where Creators and developers can define colours, fonts and custom CSS.

## Colours 
Four palette colours are defined here. These colours are used as default throughout the theme, and will also be available as 'Palette colours' in any colour picker when editing the site.
- Primary colour - main design colour. Applied to anchor tags by default
- Secondary colour - secondary brand colour
- Site background colour - the site's (body) background colour
- Site text colour - the colour used for most text

The colours will be declared as root variables on runtime:
```
:root {
    --primary: #bbcfcf;
    --secondary: #eeece6;
    --body-bg: #f7f7f9;
    --body-color: #466169;
}
```

## Fonts
Fonts can be uploaded and defined here:
- Headings font family - Used by default in all `h1` - `h6` tags
- Body font family - Used by default in paragraphs, links and remaining elements

The fonts will be declared as root variables on runtime:
```
:root {
    --font-family-base: "Open Sans";
    --headings-font-family: "Oswald";
}
```

More than two fonts can be uploaded however they will not automatically be declared as root variables.

## Custom CSS
Custom CSS can be added here that will override the default compiled CSS file (/style.css). This is available to all Creators with or without developer access.