---
layout: default
title: Canvas lint
parent: Developer tools
nav_order: 2
---

# Canvas lint

Easol has developed and maintains a gem called easol-canvas, which is used for validating Easol themes (See [RubyGems](https://rubygems.org/gems/easol-canvas) or [GitHub](https://github.com/easolhq/canvas)).

The `canvas lint` command will run the following validation checks:

1. RequiredFilesCheck
    1. Checks that the required files exist and are not empty:
        1. templates/product/index
        2. templates/blog_overview/index
        3. templates/blog_post/index
        4. partials/footer/index
        5. partials/menu/index
        6. assets/index.css
2. ValidHtmlCheck
    1. Validates all `.html` files contain valid HTML.
3. ValidLiquidCheck
    1. Validates all `.html` and `.liquid` files contain valid Liquid.
4. ValidJsonCheck
    1. Validates all `.json` files contain valid JSON.
5. ValidSassCheck
    1. Validates all `.css`, `.scss` and `.sass` files contain valid SASS.
6. ValidBlockSchemasCheck
    1. Validates the schema defined in the front matter within each block template
        1. Correctly formatted
        2. For each attribute, the required key (type) is present
        3. All keys are valid, and types exist
7. ValidMenuSchemaCheck
    1. Validates the schema in partials/menu/index.html
8. ValidFooterSchemaCheck
    1. Validates the schema in partials/footer/index.html
9. ValidCustomTypesCheck
    1. Validates all custom types are valid with valid attribute definitions

## Usage

To use the gem locally, you can install it and use the `canvas lint` command in the root of your theme directory:

```jsx
gem install easol-canvas
canvas lint
```

There is a [canvas-linter-action](https://github.com/easolhq/canvas-linter-action), which should be [set up](https://github.com/easolhq/canvas-linter-action/blob/main/README.md) inside a theme repo to run validations on each push. 
