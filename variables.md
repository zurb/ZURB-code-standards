Foundation for Apps has many, many settings variables, so it's important that we write them the same way to keep things consistent.

## Hierarchy

Only use the hyphen to denote hierarchy, not to separate words. Use this format:

```
$component-subcomponent-property-state
```

## Component names

Condense the name of the component into one word.

```scss
// Button
$button-background: #000;

// Title bar
$titlebar-background: #000;
```

## Property names

For common CSS properties, use these terms:

Variable name | CSS property
------------- | ------------
font-size     | font-size
font-weight   | font-weight
color         | color
background    | background, background-color
border        | border
shadow        | box-shadow
radius        | border-radius
padding       | padding
margin        | margin
width         | width
height        | height

## Property use

Avoid creating variables for individual facets of one property; use the shorthand versions instead. For example, create one variable for border instead of three.

```
// Good
$input-border: 1px solid #ccc;

// Bad
$input-border-width: 1px;
$input-border-style: solid;
$input-border-color: #ccc;

## State

States should always come last in the variable name. The most common states are hover, active, and focus.

```scss
$button-background-hover: #666;
$button-background-active: #333;
```

## Documentation

All variables should be documented with a description and type. Follow the [SassDoc](http://sassdoc.com/annotations) standards to describe variables.

```scss
/// Default background color for buttons.
/// @type Color
/// @since 6.1.0
$button-background: $primary-color;
```

### Description

To keep variable descriptions consistent, word it as if you're finishing the sentence "This variable sets the...".

```scss
/// Default padding for buttons.
$button-padding: 1rem;

/// Background of the page.
$body-background: #fff;
```

### `@type`

The type is the... *type* of value a variable allows.

```scss
/// Default background color for buttons.
/// @type Color
$button-background: #000;
```

If a variable can accept multiple types, separate them by a pipe. This is common for margin and padding variables, which can be a single value (a Number) or multiple values (a List).

```scss
/// Default padding for buttons.
/// @type Number | List
$button-padding: 1rem;
```

### `@since`

If a variable is added after a major patch, note the version number it was added in. This helps users on older versions know if they can or can't use a variable.

```scss
/// Default box shadow for buttons on hover.
/// @type List
/// @since 6.1.0
$button-shadow-hover: 0 2px 10px rgba(#000, 0.15);
```