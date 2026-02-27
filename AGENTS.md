# AGENTS.md - KafuCafe Shopify Theme

## Project Overview

Shopify theme (Vessel v3.4.0 by Shopify) for KafuCafe. Standard Shopify architecture with Liquid templating, CSS, and vanilla JavaScript web components.

## Project Structure

```
assets/       # JavaScript, CSS, SVG icons
blocks/       # Theme blocks (underscore prefix: `_block-name.liquid`)
config/       # Theme settings (settings_schema.json, settings_data.json)
layout/       # Layout templates (theme.liquid, password.liquid)
locales/      # Translation files (en.default.json, etc.)
sections/     # Theme sections
snippets/     # Reusable Liquid partials
templates/    # Page templates (JSON format)
```

## Build/Development Commands

No build system. Use Shopify CLI:

```bash
shopify theme dev          # Preview locally
shopify theme push         # Push to Shopify
shopify theme pull         # Pull changes
shopify theme check        # Lint/validation
shopify theme check --path sections/header.liquid  # Check specific file
```

## Liquid Code Style

- Use 2-space indentation
- Use `{% liquid %}` blocks for multi-line logic
- Use `{%- -%}` for whitespace control when appropriate
- Place `{% schema %}` at the end of section files
- Translation keys: `"name": "t:names.header"` → `locales/en.default.json`

```liquid
{% liquid
  assign variable = value
  if condition
    # logic
  endif
%}

{% render 'snippet-name', param: value %}

{% stylesheet %}
  .component-class { property: value; }
{% endstylesheet %}
```

## JavaScript Code Style

ES modules with `@theme/*` path alias (maps to `./assets/*`).

### Web Components

```javascript
import { Component } from '@theme/component';

class MyComponent extends Component {
  connectedCallback() {
    super.connectedCallback();
  }
  handleClick(event) { /* ... */ }
}

customElements.define('my-component', MyComponent);
```

### Refs Pattern

```html
<button ref="submitBtn">Submit</button>
<button ref="items[]">Item 1</button>
```

```javascript
this.refs.submitBtn  // HTMLElement
this.refs.items      // Array<HTMLElement>
```

### Event Delegation

```html
<button on:click="/handleClick">Click</button>
<button on:click="#my-component/handleClick">Click via ID</button>
```

### JSDoc Types

```javascript
/**
 * @param {string} value
 * @returns {boolean}
 */
function validate(value) { ... }
```

## CSS Conventions

- CSS custom properties extensively: `--color-*`, `--font-*`, `--padding-*`
- Mobile-first, breakpoint at 750px
- BEM-inspired: `.block__element--modifier`
- Utility classes: `.mobile:hidden`, `.desktop:hidden`, `.visually-hidden`

## Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| Sections | `kebab-case.liquid` | `product-information.liquid` |
| Snippets | `kebab-case.liquid` | `product-card.liquid` |
| Blocks | `_kebab-case.liquid` | `_header-logo.liquid` |
| JS files | `kebab-case.js` | `header.js` |
| Custom elements | `kebab-case` (hyphen required) | `header-component` |
| JS classes | `PascalCase` | `HeaderComponent` |
| Methods | `camelCase` | `handleClick` |
| Private methods | `#methodName` | `#updateRefs` |

## Error Handling

```liquid
{%- if link == blank -%}
  <a role="link" aria-disabled="true">
{%- else -%}
  <a href="{{ link }}">
{%- endif -%}
```

```javascript
try {
  await someAsyncOperation();
} catch (error) {
  console.error('Operation failed:', error);
}
```

## Accessibility

- Include skip-to-content links
- Use `aria-*` attributes appropriately
- Use `visually-hidden` class for screen-reader content

```html
{% render 'skip-to-content-link', href: '#MainContent', text: 'accessibility.skip_to_text' %}
<span class="visually-hidden">Screen reader text</span>
```

## Important Notes

- NO comments in production code unless absolutely necessary
- NO external dependencies - vanilla JS only
- NO secret keys or API credentials in theme files