---
layout: default
title: Site Styles
has_children: true
parent: Guides
nav_order: 3
---

**My Site > Style** is where creators and developers can define colours, fonts and custom CSS.

## Colours 
Four palette colours are defined here. These colours are used as default throughout the theme, and will also be available as 'Palette colours' in any colour picker when editing the site.
- Primary colour - main design colour, predominantly used across the website and applied by default to main actions
- Secondary colour - secondary colour, used in background in some elements and for buttons with secondary actions
- Site background colour - the site's (body) background colour
- Site text colour - the colour used for most text and links

The colours will be used as root variables on runtime:
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
- Headings font family - Used by default in all titles and buttons
- Body font family - Used by default in paragraphs, links and remaining elements

The fonts will be used as root variables on runtime:
```
:root {
    --font-family-base: "Open Sans";
    --headings-font-family: "Oswald";
}
```

More than two fonts can be uploaded but will not be used in root variables, will need to be referred to by CSS

## Custom CSS
Custom CSS can be added here that will override the default compiled CSS file (/style.css). Ideally this should only be used for small fixes while structural changes should be done in the Theme.