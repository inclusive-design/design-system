# Design System

Design system practices for the Inclusive Design Research Centre.

## Design Tokens

### Naming Convention

Design tokens should be named as follows:

```
system - category - concept - [concept-variant] - [property] - [property-variant] - [state]
```

#### Practical examples

Colors:

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
  /* system - category - concept - property - state */
  --idrc-color-button-background-default: oklch(0.4724 0.2127 270.65);
  --idrc-color-button-background-hover: oklch(0.3668 0.0889 286.32);
  /* system - category - concept - concept-variant - property - state */
  --idrc-color-button-secondary-background-default: oklch(0.9423 0.0235 256.1);
}
