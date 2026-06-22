# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

NovaMart is a static front-end e-commerce demo site with no build system, framework, or dependencies. It consists of four files:

- `index.html` — Shop page with product grid and cart logic (vanilla JS inline)
- `about.html` — Static about/team page
- `help.html` — Help Center page with FAQs (collapsible `<details>`/`<summary>` accordion, no JS)
- `style.css` — All shared styles for every page

## Running the Site

Open either HTML file directly in a browser, or serve with any static file server:

```
npx serve .
# or
python -m http.server
```

## Architecture Notes

- All JavaScript lives inline in `index.html` — no external scripts or modules. `about.html` and `help.html` are pure HTML/CSS.
- The `cart` array is in-memory only; it resets on page reload and is not shared between pages (the cart badge on `about.html`/`help.html` is always 0).
- Product data is a hardcoded array in `index.html`; adding products means editing that array.
- The `<nav>` markup is duplicated across all three pages — adding or renaming a page means updating the nav `<ul>` in each one and setting `class="active"` on the current page's link.
- `style.css` serves every page; it has a clear section structure (NAV, HERO, PRODUCTS, TOAST, ABOUT PAGE, HELP / FAQ PAGE, FOOTER). The About and Help pages reuse the `.about-hero` banner.
- Color palette: `#1a1a2e` (dark navy), `#e94560` (accent red), `#f8f9fa` (background).
