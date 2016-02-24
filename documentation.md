# Documentation style

## HTML

- Refer to HTML elements as *elements*, not *tags*.
- Reference elements using the actual tag, with angle brackets, formatted as code.
  - Example: `<a>`
- Format classes as code, with a leading period.
  - Example: `.secondary`
- Be explicit when referring to classes or attributes to add to an element.
  - Example: "Add the `.large` *class* to a button to make it larger."
  - Example: "Add the `data-equalize` *attribute* to the container element."

## CSS

- Use proper terminology when referring to the elements of CSS.
  - *Selectors* define what elements are affected by a ruleset.
    - Examples: `.button`, `.menu-bar > li`
  - *Properties* are styles that can be applied to a selector. It's the part before the colon.
    - Examples: `color`, `background`
  - *Values* are specific uses of properties. It's the part after the colon.
    - Examples: `#fff`, `1px solid black`

## Sass

- Sass is not all-caps for some reason, even though it's an acronym. So don't write "SASS".
- Refer to variables with the dollar sign and format them as code.
  - Example: `$primary-color`.
- When referring to functions or mixins, format them as code, with parentheses at the end.
  - Example: `clearfix()`
  - When writing about Sass, always be clear about if you're describing a mixin or a function, because the syntax for the two is the same.
- Refer to the customizable bits of functions/mixins as *parameters*. (Don't call them variables, as that would confuse it with a settings variable.)
- When writing an example mixin, always place it inside an example class selector.
```scss
.component {
  @include button;
}
```
- When writing an example mixin with multiple properties, write out the parameter names so it's clear which one does what.
  - Example: `@include button($size: medium, $background: pink);`
- When writing an example mixin with *no* properties, include it without parentheses.
```scss
.component {
  @include button;
}
```
- Refer to the settings file as "the settings file", not "`_settings.scss`".
  - Also, always link to the settings file section of the documentation.

## JavaScript

- JavaScript is always intercapped, so capitalize dat S.
- Don't refer to JavaScript as "JS".
- Refer to plugin methods as *functions*, as it's a more familiar term.
- Like with Sass, refer to the properties of functions as *parameters*.

## Callouts

Use the `.callout` pattern to highlight important information for developers. Use these colors for specific uses:

- `.primary`: tips and tricks, external links
- `.warning`: usage warnings, caveats
- `.alert`: known issues, deprecation notices
