# Design

The visual contract for this site. Any value in the CSS that contradicts this file is a defect.
The look is warm and simple: a cream page, a deep red brand color, and serif headings. The CSS
is kept at a beginner level, so values are written directly in each rule (no CSS variables).

> Maintained under Structure. Add a value here in the same change that introduces it in code.

## Foundations

- **Styling system:** plain CSS, one file, `css/style.css`
- **Values:** written directly in each rule, taken from the tables below
- **Color modes:** light only

## Color

| Value | Name | Used for |
| --- | --- | --- |
| `#b91c1c` | Red (brand) | Links, `h3`, intro fill, table header, button |
| `#991b1b` | Dark red | Link and button hover |
| `#ffffff` | White | Header, cards, TOC, table, form; text on red |
| `#fef2f2` | Light pink | Nav hover, table group rows |
| `#fffbf7` | Cream | Page background |
| `#fecaca` | Pink border | All borders and dividers |
| `#450a0a` | Red-brown | Body text |
| `#6b4f4f` | Muted brown | Captions |

Text on the red intro is white. Light pink on red is too hard to read.

## Typography

- **Headings and site title:** `"PMingLiU", serif`
- **Body:** `"Microsoft JhengHei", sans-serif`, line height 1.7

| Role | Size |
| --- | --- |
| Headings | Browser default sizes |
| Site title | 24px |
| Body, inputs, button | 16px |
| Captions | 14px |

## Spacing

| Value | Used for |
| --- | --- |
| 4px | Label to input |
| 8px | Header top/bottom padding, caption gap |
| 10px | Nav link, input, and button padding |
| 12px | Table cell padding |
| 16px | Card padding, form field gap, phone page padding |
| 24px | TOC padding, gap between radio choices |
| 32px | Page padding, card gap, form padding |
| 48px | Gap between sections, intro top/bottom padding |
| 1040px | Content max width, centered with `margin: 0 auto` |

## Corners and borders

| Value | Used for |
| --- | --- |
| 6px radius | Images, inputs |
| 12px radius | Cards, intro, TOC, form |
| 20px radius | Button |
| 1px solid `#fecaca` | Cards, TOC, table cells, inputs, form |

## Breakpoints

| Max width | Changes |
| --- | --- |
| 768px | One card per row, smaller page padding |

## Components

| Concern | Rule |
| --- | --- |
| Header | White, 4px red top border, serif site title left, menu right |
| Nav link | Plain text link; hover = light pink fill + red text |
| Intro (`.intro`) | First section of every page: red fill, white centered text, holds the `h1` |
| Table of contents (`.toc`) | White bordered box after the intro on topic pages |
| Card grid (`.card-list`) | Two cards per row (48% wide), one per row below 768px |
| Food card (`.card`) | White, 1px border, 12px corners |
| Image | Full card width, 250px tall (cropped with `object-fit: cover`), 6px corners, always in a `figure` |
| Photo files | 800px-wide JPG in `images/`, named after the dish in kebab-case |
| Table | Full width, white, every cell bordered, red header row |
| Table group row (`.table-group`) | Light pink fill, red text |
| Form | White bordered panel with 32px padding |
| Input | Full width, 1px border, 6px corners |
| Button | Red, rounded, white text, darker red on hover |
