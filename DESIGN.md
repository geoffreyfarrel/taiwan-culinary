# Design

The visual contract for this site. Any value in the CSS that contradicts this file is a defect.
The look is warm and appetizing: a cream page, a deep red brand color, a warm gold accent, and
serif headings with an editorial feel. Palette from the ui-ux-pro-max "Restaurant/Food
Service" profile, adjusted for contrast.

> Maintained under Structure. Add a token here in the same change that introduces it in code.
> Never hardcode a value this file could name.

## Foundations

- **Styling system:** plain CSS, one file
- **Theme source of truth:** the `:root` block at the top of `css/style.css`
- **Color modes:** light only
- **Base unit:** 8px grid (4px allowed for small inner gaps)

## Color

Code refers to the variable, never the hex. Contrast ratios were measured against the
background each color is used on.

| Token | Value | Used for | Contrast |
| --- | --- | --- | --- |
| `--color-primary` | `#b91c1c` | Links, `h3`, hero and button fill, table header, current nav item | 6.3:1 on page |
| `--color-primary-dark` | `#991b1b` | Link and button hover | 8.3:1 with white |
| `--color-primary-foreground` | `#ffffff` | Text on red | 6.5:1 on primary |
| `--color-tint` | `#fef2f2` | Light red fill: nav hover, TOC pills, card lists, table row hover | — |
| `--color-accent` | `#a16207` | Gold: hero bottom edge, focus ring, table group labels | 4.9:1 on white |
| `--color-background` | `#fffbf7` | Page background (warm cream), input fill | — |
| `--color-surface` | `#ffffff` | Header, cards, TOC, table, form panel | — |
| `--color-border` | `#fecaca` | All borders and dividers | — |
| `--color-foreground` | `#450a0a` | Body text (deep red-brown), footer background | 15.7:1 on page |
| `--color-muted` | `#6b4f4f` | Captions, table caption, table note | 7.1:1 on page |
| `--color-footer-text` | `#fde9d9` | Text on the dark footer | 13.7:1 on footer |

**Rules**

- Red is the brand color; gold is a small accent only. Use gold only on white, never on the tint.
- Text on the red hero is white. Light pink on red fails contrast.

## Typography

- **Headings (`--font-heading`):** `"Noto Serif TC", "Songti TC", "PMingLiU", serif` — system
  Chinese serif fonts, no download.
- **Body (`--font-body`):** `"PingFang TC", "Microsoft JhengHei", "Noto Sans TC", sans-serif`.

| Role | Variable | Size | Weight | Line height | Notes |
| --- | --- | --- | --- | --- | --- |
| H1 (page title) | `--font-size-h1` | 2.5rem (40px) | 700 | 1.3 | Serif, `letter-spacing: 0.05em`; 28px below 768px |
| H2 (section) | `--font-size-h2` | 1.75rem (28px) | 700 | 1.3 | Serif, 6px red bar on the left |
| H3 (article / dish) | `--font-size-h3` | 1.25rem (20px) | 700 | 1.4 | Serif, red |
| Site title | — | 1.5rem (24px) | 700 | — | Serif, red, `letter-spacing: 0.1em` |
| Body | `--font-size-body` | 1rem (16px) | 400 | 1.7 | |
| Hero paragraph | — | 1.125rem (18px) | 400 | 1.7 | Max 680px wide, centered |
| Small / caption | `--font-size-small` | 0.875rem (14px) | 400 | 1.5 | |

## Spacing

Scale: 8px steps.

| Variable | Value | Used for |
| --- | --- | --- |
| `--space-xs` | 4px | Label to input, nav item gap |
| `--space-sm` | 8px | List item spacing, header vertical padding |
| `--space-md` | 16px | Card padding, paragraph margin, table cell padding |
| `--space-lg` | 32px | Gap between cards, page side padding, form padding |
| `--space-xl` | 64px | Gap between sections, hero vertical padding |

| Context | Value |
| --- | --- |
| Content max width | `--content-width` 1040px, centered with `margin: 0 auto` |
| Control height | `--control-height` 44px minimum for nav links, TOC pills, inputs, buttons |

## Radius, borders, elevation

| Variable | Value | Used for |
| --- | --- | --- |
| `--radius-sm` | 6px | Inputs, images, card ingredient box |
| `--radius-md` | 12px | Cards, hero, TOC, table, form panel |
| `--radius-full` | 999px | Nav links, TOC pills, button |
| Border width | 1px solid `--color-border` | Cards, tables, inputs |
| `--shadow-card` | `0 1px 3px rgba(69, 10, 10, 0.08)` | Cards and form at rest |
| `--shadow-raised` | `0 8px 20px rgba(69, 10, 10, 0.12)` | Card on hover |

## Breakpoints

Desktop first, checked at 390px phone width.

| Name | Max width | Changes |
| --- | --- | --- |
| narrow | 768px | One card per row, smaller side padding, smaller `h1`, hero padding reduced |

## Component conventions

| Concern | Rule |
| --- | --- |
| Header | White, 4px red top border, serif red site title left, nav right |
| Nav link | Pill, 44px tall; hover = tint fill + red text; current page (`aria-current`) = red fill + white text |
| Intro / hero (`.intro`) | First section of every page: red fill, white centered text, 6px gold bottom border, holds the `h1` |
| Table of contents (`.toc`) | White box after the hero on topic pages; links are tinted pills in a wrapping row |
| Card grid (`.card-list`) | Two cards per row (48.5% wide), one per row below 768px |
| Food card (`.card`) | White, 1px border, `--radius-md`, `--shadow-card`; on hover lifts 3px with `--shadow-raised` |
| Card list | The `ul` inside a card sits in a tint box with `--radius-sm` |
| List markers | Bullets and numbers are red and bold (`li::marker`) |
| Image | Full card width, `--radius-sm`, always in a `figure`; topic pages add a `figcaption` |
| Photo shape | Cropped to 16:10 with `object-fit: cover` so cards line up. Add class `focus-bottom` when the subject sits low in the photo |
| Photo files | 800px-wide JPG in `images/`, named after the dish in kebab-case |
| Photo credits (`.credits`) | Last section of every page that shows photos: small muted text, one `li` per photo with source link, author, and license link |
| Table | White, rounded, 1px outer border, row dividers only; red header row; row hover = tint |
| Row header (`th scope="row"/"rowgroup"`) | Tint fill, red text |
| Table group row (`.table-group`) | `th colspan` spanning the table, gold text, wide letter spacing |
| Form | White panel with `--space-lg` padding and `--shadow-card` |
| Input | 44px tall, cream fill, 1px border, border turns red on hover |
| Radio group (`.radio-group`) | 1px bordered box, `--radius-sm`, bold question on top |
| Radio | 18px, `accent-color` primary; label is a 44px tall click target |
| Button | Red pill, bold white text, darker red on hover |
| Focus | 3px gold outline with 2px offset on every link and control (`:focus-visible`) |
| Footer | Dark red-brown fill, cream text, centered |

## Motion

| What | Effect | Duration |
| --- | --- | --- |
| Link, nav, button, TOC pill, input | Color / background / border-color change | `--transition` 0.2s ease |
| Card hover | Lift 3px and stronger shadow | 0.2s ease |
| `prefers-reduced-motion: reduce` | All transitions off, no card lift | — |
