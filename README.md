# Design System

Design system practices for the Inclusive Design Research Centre.

## Design Tokens

### Naming Convention

Design tokens should be named as follows:

```
system - [element] - [element-variant] - category - [concept] - [concept-variant] - [property] - [property-variant] - [states]
```

#### Practical examples

Colors (as primitive tokens, these do not have a property):

```css
:root {
  /* system - category - concept - concept-variant */
  --idrc-color-primary-100: oklch(0.987 0.0062 255.47);
  --idrc-color-primary-500: oklch(0.7934 0.1314 224.2);
}
```

Buttons:

```css
:root {
  /* system - element - category - property - state */
  --idrc-button-color-surface-default: oklch(0.4724 0.2127 270.65);
  --idrc-button-color-surface-hover: oklch(0.3668 0.0889 286.32);
  /* system - element - element-variant - category - property - state */
  --idrc-button-secondary-color-surface-default: oklch(0.9423 0.0235 256.1);
}
```

Links:

```css
:root {
  /* system - element - category - property - states */
  --idrc-link-color-content-hover: oklch(0.3668 0.0889 286.32);
  --idrc-link-color-content-hover-visited: oklch(0.4724 0.2127 270.65);
}
```
