# CSS

## Class naming

ZURB doesn't adhere to a strict class standard, so here are some general guidelines.

Class names should have hyphens, and no underscores or capital letters.

```css
.button {}
.menu-bar {}
```

When styling sub-elements of a component, prefer writing a new class over using a tag selector if possible. This reduces selector specificity, making it easier for the user to override default styles. It also reduces the risk that tag styles will leak into other elements.

```css
// Okay
.menu-bar > li {}
// Better
.menu-bar-item {}
```

When writing classes in this style, don't nest the selector inside its parent. The purpose of nesting is to create scope, but by including the parent's class name in the child class, you've already effectively scoped it.

```css
// Bad
.menu-bar .menu-bar-item {}

// Good
.menu-bar-item {}
```

When styling a tag, consider using the child selector to prevent conflicts, *especially* for structural components that could include any HTML inside of it.

```css
// Problematic, because now *every* <li> inside tabs will be styled this way
.tabs li {}
// Better, because you've restricted the reach of the selector
.tabs > li {}
// Even better, because you've reduced specificity
.tabs-item {}
```

For really generic class names, or class names that are used in multiple components, chain them to the main class. In Foundation we often re-use the same class names for different components, so each instance needs to be isolated from the others. It's also possible that other libraries, or the user's own styles, would clash with a generic word.

```css
.button.primary {}
.switch.large {}
```
