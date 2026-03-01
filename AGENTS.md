# AGENTS.md - KafuCafe Theme Development Guide

## Overview

This is a Shopify theme based on **Horizon** - a first-party Shopify theme. Uses Liquid for server-side rendering, vanilla JavaScript with Web Components, and modern CSS. No Node.js build step - pure Shopify theme.

---

## Build / Lint / Development Commands

### Commands
```bash
shopify theme dev              # Development server
shopify theme check            # Lint/validate theme
shopify theme check --auto-fix # Auto-fix issues
shopify theme push             # Push to store
shopify theme publish          # Deploy to production
```

**Note:** No traditional unit tests - validation via Theme Check.

---

## Code Style Guidelines

### General Principles
- **Zero external dependencies** - Use native browser APIs only
- **Server-rendered HTML** - All content via Liquid
- **Progressive enhancement** - Works without JS
- **Evergreen web** - Latest browser features; no polyfills

---

### JavaScript Standards (`assets/*.js`)

- Use `const` over `let` unless necessary
- Use `for (const item of items)` over `items.forEach()`
- Use Web Components via Component framework (`assets/component.js`)
- Always use async/await over `.then()` chaining

```javascript
import { Component } from '@theme/component';
class MyComponent extends Component {
  requiredRefs = ['element'];
  connectedCallback() { super.connectedCallback(); }
}
customElements.define('my-component', MyComponent);
```

#### Error Handling
```javascript
const fetchData = async (url) => {
  try {
    const response = await fetch(url);
    if (!response.ok) throw new Error(`HTTP ${response.status}`);
    return await response.json();
  } catch (error) {
    console.error('Fetch error:', error);
    return null;
  }
};
```

---

### CSS Standards (`assets/*.css` or `{% stylesheet %}`)

- **Never** use IDs as selectors
- **Avoid** elements as selectors
- **Avoid** `!important` - only with comment explaining why
- Target `0 1 0` specificity (single class)

#### BEM Naming
```css
.block { }
.block__element { }
.block--modifier { }
```

#### CSS Variables
- Always use CSS variables for colors (never hardcode)
- Namespace: `--component-property`
- Global variables in `snippets/theme-styles-variables.liquid`

#### Modern Features
- Container queries, `clamp()` for fluid spacing
- Logical properties (`padding-inline`, `margin-block`)
- Mobile-first media queries (`min-width`)

#### Nesting Rules
- No `&` operator in nested selectors
- Never nest beyond first level (except media queries/states)
```css
.component {
  @media screen and (min-width: 750px) { width: 100px; }
}
```

---

### Liquid Standards (`*.liquid`)

#### CRITICAL: Schema Editing
**NEVER edit `{% schema %}` blocks directly!**
- Edit `.js` files in `schemas/blocks/` or `schemas/sections/`
- Run `npm run build:schemas` to regenerate Liquid files

#### Syntax Rules
- Use `{% liquid %}` for multiline code
- Use `{% # comment %}` for inline comments
- Use dot notation: `product.title` not `product['title']`

#### Inline Variables Pattern
```liquid
<div class='component--{{ settings.style }}'>
  {{ content | truncate: 200 }}
</div>
```
Exceptions: Complex filter parameters, same calculation used multiple times.

#### Snippet Documentation
```liquid
{% doc %}
  Snippet Name
  Description of what it does.
  @param {object} param - Description
  @example
  {% render 'snippet-name', param: value %}
{% enddoc %}
```

---

### HTML Standards (in `.liquid` files)

- Use `<details>/<summary>` for expandables
- Use `<dialog>` for modals
- Use `popover` attribute for tooltips
- Use `<search>` for search forms

#### Accessibility
- All images must have `alt` text
- Use semantic HTML (`<main>`, `<nav>`, `<section>`, etc.)
- Ensure focus indicators are visible
- Support keyboard navigation

---

### File Structure
```
assets/        # JavaScript and CSS (*.js, *.css)
blocks/        # Shopify blocks (JSON)
config/        # Theme settings
layout/        # Theme templates (theme.liquid)
locales/       # Translation files (*.json)
sections/      # Theme sections (*.liquid)
snippets/      # Reusable Liquid partials (*.liquid)
templates/    # Page templates (*.json)
schemas/      # Schema source (JS) - generates Liquid
```

---

### Cursor Rules (Applied)

This project includes Cursor rules in `.cursor/rules/`:

- `javascript-standards.mdc` - JS/Web Components patterns
- `css-standards.mdc` - CSS, BEM, variables  
- `liquid.mdc` - Liquid syntax, schema generation
- `html-standards.mdc` - Modern HTML elements
- `*accessibility*.mdc` - WCAG requirements
- `schemas.mdc` - Schema file structure

---

### Best Practices

1. Test locally with `shopify theme dev` before pushing
2. Run Theme Check before committing: `shopify theme check`
3. Use progressive enhancement - works without JS
4. Follow accessibility standards (see Cursor rules)
5. Use semantic HTML - meaningful structure
6. Keep CSS scoped - use BEM and CSS variables
7. Document snippets with `{% doc %}` tags
