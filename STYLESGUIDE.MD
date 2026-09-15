# Styling Guide

This project uses a simple component-based CSS structure. Styles are split into global foundation styles, layout utilities, and component-specific styles.

## CSS structure

```text
css/
  base.css
  layout.css
  components/
    button.css
    components.css
    footer.css
    forms.css
    header.css
    hero.css
    main.css
    nav.css
    tables.css
```

## CSS naming conventions

- Use lowercase letters and hyphens to separate words.
- Use descriptive names that reflect the purpose of the style.
- Avoid using abbreviations unless they are widely recognized.
- Use consistent naming conventions throughout the project.

## File responsibilities
### [css/base.css](css/base.css)

Use this file for:
- browser defaults and reset styles
- global design tokens
- body typography
- shared accessibility/helper classes

Do not place component-specific styles here.

### [css/layout.css](css/layout.css)

Use this file for:
- page-level layout helpers
- reusable layout wrappers
- structural utilities

Current layout classes:
- `.container`
- `.page-shell`
- `.page-link`

### [css/components/*.css](css/components/*.css)

Use component files for styles that belong to a specific UI area.
Examples:

- [header.css](css/components/header.css) for header and brand styles
- [nav.css](css/components/nav.css) for navigation styles
- [button.css](css/components/button.css) for button styles
- [forms.css](css/components/forms.css) for form page and form controls
- [tables.css](css/components/tables.css) for table page and table components

## Design tokens
Global tokens live in [css/base.css](css/base.css).

## Width

``` css
--max-width: 1100px;
```

Use this for  ain content wrappers through `.container`.

## Colors

``` css
--color-text: #1f2937;
--color-bg: #ffffff;
--color-muted: #f3f4f6;
--color-border: #e5e7eb;
--color-accent: #0a74da;
```

Usage:
- `--color-text` for primary text
- `--color-bg` for white/default surfaces
- `--color-muted` for light background sections and subtle hover states
- `--color-border` for borders
- `--color-accent` for links, primary actions, and focus states

Avoid adding one-off color variables unless the color is reused across multiple components.

## Spacing scale

``` css
--space-1: 0.25rem;
--space-2: 0.5rem;
--space-3: 0.75rem;
--space-4: 1rem;
--space-5: 1.25rem;
--space-6: 1.5rem;
--space-7: 1.75rem;
--space-8: 2rem;
--space-10: 2.5rem;
--space-11: 10rem;
```

Use spacing tokens for margin, padding, gaps, and consistent component rhythm.

Avoid using spacing tokens as font sizes unless the value intentionally matches the scale.

## Typography
The project uses:

``` css
font-family: "Segoe UI", Tahoma, sans-serif;
```

This is set globally on `body`.

Component styles should normally inherit the global font with:

``` css
font: inherit;
```

Use uppercase, letter spacing, and heavier font weights for labels, navigation, and small headings.

## Borders and radius

The standard component radius is:
``` css
border-radius: 0.5rem;
```

The standard border is:
``` css
border: 1px solid var(--color-border);
```

Use these for cards, forms, buttons, tables, and shell components.

## Shadows
Use subtle shadows only:

``` css
box-shadow: 0 2px 8px rgba(15, 23, 42, 0.04);
```

Avoid heavy shadows unless a component intentionally needs stronger emphasis.

## Buttons

Button styles live in:

``` text
css/components/button.css
```

Use the shared button classes:

``` html
<a class="button button-primary" href="#">Primary</a>
<a class="button button-secondary" href="#">Secondary</a>
```

Do not redefine `.button`, `.button-primary`, or `.button-secondary` in other component stylesheets.

## Forms

Form styles live in:

``` text
css/components/forms.css
```

Primary classes:

- `.form-shell`
- `.form`
- `.form-brand`
- `.form-divider`
- `.form-field`
- `.form-label`
- `.form-input`
- `.form-select`
- `.form-textarea`
- `.choice-group`
- `.choice-option`
- `.form-actions`

Form inputs should use shared colors, borders, radius, and focus states.

## Tables
Table styles live in:

``` text
css/components/tables.css
```

Primary classes:
`.table-shell`
`.table-search`
`.table-wrapper`
`.data-table`

Tables should:

- use `border-collapse: collapse`
- use shared borders
- use muted header backgrounds
- support horizontal scrolling with `.table-wrapper`
- avoid fixed positioning or unnecessary fixed widths

## Component/demo pages
The component index page uses:
- `.shell`
- `.component-list`
- `.component-list__link`

Use these classes for lists of component demos or internal navigation cards.

## Naming conventions
Use readable class names. BEM-style naming is preferred for component parts:

``` css
.site-header__inner
.site-nav__list
.site-footer__grid
.component-list__link
```

Use modifier classes when needed:

``` css
.button-primary
.button-secondary
.form-input--range
```

## General rules

- Prefer CSS variables over hard-coded colors and spacing.
- Keep global styles in [base.css](css/base.css).
- Keep layout helpers in [layout.css](css/layout.css).
- Keep component-specific rules in the relevant component file.
- Do not duplicate shared component styles in multiple files.
- Keep hover and focus states consistent.
- Use `:focus-visible` for keyboard accessibility.
- Keep shadows, borders, and border radii visually subtle and consistent.
