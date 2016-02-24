# CSS

## Class naming

ZURB's class style is focused on readability. Here are guidelines to follow when writing CSS for Foundation.

Class names should have hyphens, and no underscores or capital letters.

```css
/* Good */
.button {}
.menu-bar {}

/* Naw */
.Button {}
.menu_bar {}
```

When styling sub-elements of a component, prefer writing a new class over using a tag selector if possible. This reduces selector specificity, making it easier for the user to override default styles. It also reduces the risk that tag styles will leak into other elements.

```css
/* Okay */
.menu-bar > li {}
/* Better */
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
/* Problematic, because now *every* <li> inside tabs will be styled this way */
.tabs li {}
/* Better, because you've restricted the reach of the selector */
.tabs > li {}
/* Even better, because you've reduced specificity */
.tabs-item {}
```

For really generic class names, or class names that are used in multiple components, chain them to the main class. In Foundation we often re-use the same class names for different components, so each instance needs to be isolated from the others. It's also possible that other libraries, or the user's own styles, would clash with a generic word.

```css
.button.primary {}
.switch.large {}
```

Dynamic classes managed by JavaScript should be prefixed with the word `.is-`. This sets them apart as a special kind of CSS class, and also ensures that UnCSS doesn't strip them out.

Some dynamic classes modify the state of an element temporarily.

```css
/* Basic tab pane */
.tab-pane {
  display: none;
}

/* Tab pane made visible */
.tab-pane.is-active {
  display: block;
}
```

Other dynamic classes apply structural logic necessary for a plugin to function. The menu plugins are a good example of this.

```css
/* Applied to the top-level <ul> of a dropdown menu */
.is-dropdown-menu {}

/* Applied to nested <ul>s in a dropdown menu */
.is-dropdown-submenu {}

/* Applied to <li>s that house a nested <ul> */
.is-dropdown-submenu-parent {}
```
