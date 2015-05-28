# Mixins

## Types of Mixins

Components mixins should be structured atomically, so each mixin implements one piece of the component's functionality. There's four broad categories of mixins:

  - A base mixin with structural styles (`button-base()`)
  - A layout mixin, which defines sizing and positioning (`button-layout()`)
  - A style mixin, which defines visual styles (`button-style()`)
  - A shorthand mixin, which references all of the above (`button()`)

More complex components may require more specific mixins, while simpler components may only need one or two.

Buttons are a good example of a component with a lot of simple, atomic mixins. Each one correlates to a modifier class that works with buttons.

```scss
// Maps to .button
@mixin button-base {}

// Maps to .tiny, .small, .large
@mixin button-size {}

// Maps to .expand
@mixin button-expand {}

// Maps to .primary, .success, .error
@mixin button-style {}

// Combines all of the above
@mixin button {}
```

## Parameters

If a mixin has more than one parameter, format it like this:

```scss
@mixin component(
  $param,
  $param: value
) {
  
}
```

Otherwise, you can write it on one line:

```scss
@mixin component($param) {
  
}
```

## Property Grouping

If possible, try to separate the logic of the mixin from the actual CSS output. This makes it easy to see what CSS is actually being created.

In the below example, the `margin` property is defined based on the result of the `@if` statement. The mixin also generates more CSS at the bottom, but it's separated from the `margin` property, which is up in the `@if`/`@else` blocks.

```scss
@mixin row($behavior: default) {
  @if $behavior == default {
    margin: 0 auto;
  } @else {
    margin: 0 -1rem;
  }

  max-width: 1000px;
  clear: both;
}
```

This mixin could be improved by moving the `margin` property down with the other CSS. To do this, we'll store the value in a variable. Now we can see that this mixin generates 3 CSS properties, determined by the logic at the beginning.

```scss
@mixin row($behavior: default) {
  @if $behavior == default {
    $margin: 0 auto;
  } @else {
    $margin: 0 -1rem;
  }

  margin: $margin;
  max-width: 1000px;
  clear: both;
}
```

## CSS Output

If possible, the CSS output of a component should be written entirely with mixins. This also serves as a proof-of-concept for the mixins: are they thorough enough to work for the end user?

If you find yourself patching the CSS output with extra properties, try to incorporate them into a mixin instead. Remember that if the user turns off the default CSS for that component, they only have access to the mixins, not any of the default CSS, which would include any patches.
