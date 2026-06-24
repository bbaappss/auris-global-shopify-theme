# Auris theme — setup notes

This theme reproduces the Auris Lovable blueprint as an editable Shopify theme.
The **Home page** works out of the box. The other pages are Shopify **page
templates** — you create a Page in admin and assign the matching template.

## Brand system

- **Colors / fonts / utilities:** `assets/auris.css` (loaded globally in
  `layout/theme.liquid`). Palette: navy `#0E2A40`, aurum `#C9A961`, oxblood
  `#6B2C2C`, stone `#E6E1D4`, ivory `#FAF7F2`. Fonts: Playfair Display (serif) +
  Hanken Grotesk (sans), loaded from Google Fonts.
- **Header / Footer / Email capture:** `sections/header.liquid`,
  `sections/footer.liquid`, `sections/auris-email-capture.liquid`. The email
  capture + footer render site-wide via `sections/footer-group.json`.

## Reusable sections (all editable in the theme editor)

| Section | Used for |
|---|---|
| `auris-hero` | Full-screen hero (home + Society), optional bg image & CTA |
| `auris-statement` | Centered italic statement(s) with caption rule |
| `auris-page-header` | Navy/ivory page banner (About, Calendar, legal) |
| `auris-prose` | Rich-text body (About story, Privacy, Terms) |
| `auris-event` | Event detail rows + price/reservation panel (Society) |
| `auris-features` | Three numbered columns ("What to Expect") |
| `auris-contact` | Bordered contact card with email |
| `auris-calendar` | Repeatable list of upcoming gatherings |

## Pages to create in admin

Go to **Online Store → Pages → Add page**, set the title, then under
**Theme template** pick the listed template:

| Page title | Template to assign | Suggested handle |
|---|---|---|
| Society  | `page.society`  | `society`  |
| Calendar | `page.calendar` | `calendar` |
| About    | `page.about`    | `about`    |
| Privacy  | `page.privacy`  | `privacy`  |
| Terms    | `page.terms`    | `terms`    |

(The Home page already uses `templates/index.json` automatically.)

## Navigation menu

The header reads the **main-menu** navigation. In **Online Store → Navigation →
Main menu**, add links: Society → `/pages/society`, Calendar →
`/pages/calendar`, About → `/pages/about`. Update the footer menu similarly
(About / Privacy / Terms) on the Footer section in the theme editor.

## Images

`spirit-stadium.jpg` (Society hero) and `spirit-loge-real.png` (event) ship in
`assets/` and are wired in as fallbacks. To swap them, upload a new image in the
section's **Image** picker in the theme editor — that overrides the asset.

## Notes / follow-ups

- The email-capture form uses Shopify's native customer form and tags
  submissions `newsletter`.
- "Reserve Your Seats" currently links to the external Splash page from the
  blueprint. Point it at a Shopify product/checkout when ready.
- The Google Fonts `<link>` triggers a Theme Check "RemoteAsset" warning by
  design; move the fonts into `assets/` if you prefer self-hosting.
