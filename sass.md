# Sass

## Naming

- The official name for a component should be singular. This is most important for filenames.
  - Examples: `_panel.scss`, `panel.js`
  - Exceptions: "Forms", "Tabs", "Breadcrumbs"
- Write out components in lowercase, unless it's a title of a page.
  - Named plugins are an exception, like Reveal and Interchange.

## Filename

Start the filename with an underscore, like any Sass partial. The name of the component should be singular. One exception is "tabs", because "tab" just seems weird. If a component's name is more than one word, separate each word with a hyphen.

```
_button.scss
_media-object.scss
_tabs.scss
```

## File structure

The elements of the component should go in this order:

- Poster comment
- Settings variables
- Sass mixins
- CSS output

### Poster comment

At the top is a poster comment with copyright information.

```scss
// Foundation for Sites by ZURB
// foundation.zurb.com
// Licensed under MIT Open Source
```
