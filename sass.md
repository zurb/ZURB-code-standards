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

## Class Naming

ZURB follows a specific CSS class style guide. Refer to the [class naming](class-naming.md) page to learn more.

## Nesting

Sass makes it easy to nest, but avoid nesting CSS too deeply, as this makes for more complex selectors that will be more likely to interfere with other CSS down the road.

Follow the Inception Rule: *don't go more than three levels deep*. This amount of nesting is too much:

```scss
.element {
  .element-child {
    p {
      a {}
    }
  }
}
```

## File structure

The elements of the component should go in this order:

- Poster comment
- Settings variables
- Sass mixins
- CSS output

## Using calc()

Avoid using calc() with arbitrary values. calc() in conjunction with variables is much more readable and maintainable.

```scss
/* Bad */
calc(100vh - 150px);

/* Good */
calc(100vh - #{$main-nav-height});
```

### Poster comment

At the top is a poster comment with copyright information.

```scss
// Foundation for Sites by ZURB
// foundation.zurb.com
// Licensed under MIT Open Source
```
