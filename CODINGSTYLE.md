# Coding Style

The conventions for this repository. This file governs every change made here.
The stack was chosen by the course goal: learning HTML and CSS basics.

> Maintained under Structure. Update the stack table when a tool changes; update the
> command table when a command changes. Record a code pattern here the second time it is used.
> A stale entry here misleads every future session.

## Tech Stack

| Layer | Technology | Version | Notes |
| --- | --- | --- | --- |
| Markup | HTML | HTML5 (living standard) | Semantic elements first |
| Styling | CSS | CSS3, no preprocessor | One shared stylesheet, `css/style.css` |
| Scripting | None | — | JS may be added in the final-term phase, only when the user says so |
| Runtime | Browser | Current desktop browsers | Pages open straight from the file system |
| Dev tools | Node.js + `npx` | Node 22 | Checks only. No `package.json`, no build, nothing shipped |
| Formatting | Prettier | 3.x | Run through `npx`, config in `.prettierrc.json` |
| HTML check | html-validate | 11.x | Run through `npx`, config in `.htmlvalidate.json` |
| CSS check | Stylelint | 17.x | Run through `npx`, config in `.stylelintrc.json` |

No libraries, frameworks, CDNs, or web fonts. Adding any of them needs an ADR first.

## Commands

Run from the repo root (Git Bash or PowerShell). The first run downloads each tool.

| Purpose | Command |
| --- | --- |
| Install | none |
| Dev server | none — open `index.html` in a browser |
| Format | `npx prettier@3 --write "**/*.{html,css}"` |
| Format (check only) | `npx prettier@3 --check "**/*.{html,css}"` |
| Lint HTML | `npx html-validate@11 "**/*.html"` |
| Lint CSS | `npx stylelint@17 "**/*.css"` |
| Typecheck | n/a |
| Test | n/a — check each page by opening it in a browser |
| Build | none |

## Conventions

### Naming

- Files and folders: lowercase kebab-case English, e.g. `night-market.html`, `stinky-tofu.jpg`.
- CSS classes: lowercase kebab-case describing the role, e.g. `.food-card`, `.price-table`.
  Not appearance (`.red-text`) and not Chinese.
- `id` values: kebab-case, used for in-page links (`#oyster-omelette`) and form labels.

### Directory layout

```
index.html              Home page: intro + links to the four topics
pages/
  classic-snacks.html   1. 台灣必吃經典小吃 (Geoffrey)
  night-market.html     2. 台灣夜市美食 (Geoffrey)
  desserts-drinks.html  3. 台灣特色甜點與飲料 (partner)
  regional-food.html    4. 台灣各地特色美食 (partner)
css/
  style.css             The single shared stylesheet
images/                 Photos, one subfolder per topic if it grows
videos/                 Video files (keep them small)
```

- Every page links `css/style.css` with a relative path (`../css/style.css` from `pages/`).
- Pages 3-4 are the partner's. Until her zip arrives, the nav links for them stay as
  placeholders (`<a href="#">`) and no content is written for them.
- When merging the partner's zip: put her pages in `pages/`, move her styles into `style.css`
  (or `css/partner.css` if they clash), and bring them into line with this file and
  `DESIGN.md`.

### HTML structure

Every page follows this skeleton:

```html
<!doctype html>
<html lang="zh-Hant-TW">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>頁面名稱 | 台灣美食</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <header>…site title + <nav>…</nav></header>
    <main>
      <section>
        <h2>…</h2>
        <article>…</article>
      </section>
    </main>
    <footer>…</footer>
  </body>
</html>
```

- Use the element that means the thing: `<section>` for a themed group with a heading,
  `<article>` for one self-contained item (one dish), `<nav>` for navigation, `<figure>` +
  `<figcaption>` for a captioned image.
- Do not use `<div>` where a semantic element fits. A `<div>` is only for pure layout wrapping.
- One `<h1>` per page. Headings go in order, never skipping a level.
- Every `<img>` has a meaningful Chinese `alt`. Every `<video>` has `controls`.
- Do not use `<fieldset>` or `<legend>` (user's choice). Group radio buttons in
  `<div class="radio-group" role="radiogroup" aria-labelledby="…">` with the question in a
  `<p class="radio-group-title" id="…">`.
- Every form field has a `<label>` linked by `for`/`id`. Forms use `method="post"`; no
  backend exists, so `action` points to `#`.
- Tables have `<thead>` and `<tbody>`, header cells are `<th>`, and a `<caption>` names the
  table.
- No inline `style` attributes and no `<style>` blocks. All CSS lives in `css/style.css`.
- Keep each Chinese paragraph on one source line. A line break inside Chinese text shows up
  as a stray space in the browser.
- The header and main menu are copied identically onto every page. Only the relative paths and
  which link carries `aria-current="page"` change. Edit all pages together.
- Every `<th>` has a `scope` (`col`, `row`, `colgroup`, `rowgroup`); html-validate requires it.
- Each topic page starts with an `.intro` section holding the `h1`, then a `.toc` nav listing
  the page's sections by `#id`.
- Photos come only from freely licensed sources (Wikimedia Commons or our own). Every page that
  shows a photo lists it in its `.credits` section: source link, author, license link. A photo
  without a credit line is a defect.

### CSS

- Design values (colors, spacing, font sizes) are CSS custom properties on `:root` at the top of
  `style.css`, named as in `DESIGN.md`. Rules use `var(--…)`, never a raw hex.
- Order the file: variables, base element styles, layout (header/nav/main/footer), components
  (cards, tables, forms), then page-specific rules, each under a comment heading.
- Prefer element and class selectors. No `id` selectors, no `!important`.

### Comments

- One comment heading per section of `style.css`.
- HTML comments only to mark a large region or the partner's merged code, not to restate the
  markup.

### Reference document

`HTML-CSS-REFERENCE.md` lists every HTML tag and CSS property used in the site and what it
does. Any change that uses a new tag or property adds its row in the same change.

### Testing

No automated tests. A change is done when the three check commands pass and the page has been
opened in a browser to confirm it renders.

## Non-negotiables

These apply regardless of what surrounding code does:

- Vanilla HTML and CSS only. No JavaScript until the user says the final-term phase has started.
- No hardcoded design values — colors, spacing, and font sizes come from the variables in
  `DESIGN.md`.
- No decorative emojis in code, comments, logs, commit messages, or docs.
- Commits are atomic — one logical change each — and follow Conventional Commits.
- A pattern used twice is recorded here (code) or in `DESIGN.md` (appearance), so the third use
  follows it.
- The check commands pass before work is reported as done.
- Adding any tool, library, or new top-level folder gets an ADR and user confirmation first.

## Off-limits

| Path | Why |
| --- | --- |
| `pages/desserts-drinks.html`, `pages/regional-food.html` | The partner's topics. Only edit them when merging or adjusting her delivered code |
