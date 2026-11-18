# Design System

Design system practices for the Inclusive Design Research Centre.

## Figma Workflow

We use the [Tokens Brücke](https://github.com/tokens-bruecke/figma-plugin) plugin
to export variables from Figma.

We use the following advanced settings:

- Color Mode: OKLCH DTCG

- [ ] Split collections into separate files
- [ ] Split modes into separate files
- [ ] Omit collection names
- [ ] Include variable scopes
- [ ] Use percentage for opacity
- [x] Use DTCG keys format
- [ ] Include `.value` string for aliases
- [ ] Include Figma metadata

To obtain the Design Token JSON files from Tokens Brücke, open the plugin, confirm
that the settings are configured correctly, and then click **Download JSON** to
download the token file. With a GitHub token, it can also be synced directly to
the repo, e.g. [src/design-tokens/synced/design.tokens.json](https://github.com/inclusive-design/financial-inclusion.ca/blob/7862fe47f261f60077063c6c5ec783bc5fc6e657/src/design-tokens/synced/design.tokens.json)

Some adjustments need to be made to the downloaded file, as follows:

1. A generic UIO theme needs to be created which maps UIO primitives to different
   color tokens.
2. Dark mode and contrast themes need to be created.
3. Unnecessary group prefixes need to be removed from variable names.
4. Extraneous properties need to be removed from variables.
5. The `$type` values need to be standardized to match the DTCG spec.
6. Updated tokens need to be written to their own files in the repo.

These steps are all handled in an [`eleventy.before` hook](https://github.com/inclusive-design/financial-inclusion.ca/blob/7862fe47f261f60077063c6c5ec783bc5fc6e657/eleventy.config.js#L100).

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
