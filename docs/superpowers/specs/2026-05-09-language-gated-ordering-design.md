# Language-Gated Ordering UI

**Date:** 2026-05-09

## Problem

The menu app has four languages: Chinese (zh), English (en), Korean (ko), Japanese (ja). Local Taiwanese customers use the Chinese menu and order with paper sheets + pencils — they don't need the digital `−`/`+` ordering controls. Foreign tourists use EN/KO/JA and need the ordering system to communicate their order to the cashier.

Previously, the `−`/`+` quantity controls and cart bar were shown for all languages.

## Decision

Use **pure CSS language gating** (Approach A). No JavaScript changes.

- The body element already carries `class="lang-zh"` (or `lang-en`, `lang-ko`, `lang-ja`) when a language is active.
- CSS selectors `.lang-zh .qty-ctrl` and `.lang-zh .cart-bar` hide the ordering UI completely for Chinese mode.
- A `.tourist-hint` element is always in the DOM but CSS-hidden by default; `.lang-zh .tourist-hint` reveals it only when Chinese is active.

Cart state is not cleared on language switch (not required).

## Changes

### `css/style.css`
```css
.tourist-hint { display: none; ... }
.lang-zh .tourist-hint { display: block; }
.lang-zh .qty-ctrl     { display: none; }
.lang-zh .cart-bar     { display: none !important; }
```

### `index.html`
One new element added after `.lang-switch`:
```html
<div class="tourist-hint">
  🌏 Tap <strong>EN / 한국어 / 日本語</strong> above to place a digital order
</div>
```

## Behaviour

| Language | `−`/`+` controls | Cart bar | Tourist hint |
|----------|-----------------|----------|--------------|
| 中文 (zh) | Hidden | Hidden | Visible |
| EN / KO / JA | Visible | Visible (when cart non-empty) | Hidden |
