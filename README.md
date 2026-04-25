# RoJu Studio — Landing Page

A single-page marketing site for **RoJu Studio**, a marketing agency based in San José, Costa Rica that works with entrepreneurs and small-to-medium businesses across Latin America and the U.S. The site is in Spanish and is built as a single self-contained `index.html` file with embedded CSS and JavaScript.

## Overview

The page introduces the agency, shows what it offers, builds social proof, and pushes visitors toward booking a free 30-minute consultation. The visual style is warm and editorial — cream backgrounds, navy and yellow accents, serif display type (Fraunces), and small playful touches like a handwritten script font (Caveat), morphing blob shapes, and decorative stars.

## Sections

The page flows top-to-bottom through:

1. **Top bar + sticky nav** with logo, anchor links, and a primary CTA.
2. **Hero** — headline, lead copy, two CTAs, and an illustrated SVG composition with floating "live result" cards (reach, engagement, leads).
3. **Services** (`#services`) — three feature cards: *Branding que se recuerda*, *Contenido que conecta*, *Campañas que venden*.
4. **Social proof** — "200+ entrepreneurs helped" plus a row of client brand names.
5. **Detail rows** (`#work`) — three alternating left/right sections covering brand strategy, analytics & growth, and automations, each paired with a UI mockup (color palette, KPI dashboard, phone chat).
6. **Email capture** (`#capture`) — newsletter signup with inline success feedback.
7. **FAQ** (`#faq`) — six-question accordion (sizing, timeline, ads, contracts, geography, pricing).
8. **Final CTA** (`#about`) — invitation to book a free consultation.
9. **Footer** — brand blurb, link columns (Servicios, Empresa, Contacto), copyright, and social icons.

## Tech

- **Plain HTML, CSS, and vanilla JS** — no build step, no framework, no dependencies to install.
- **Google Fonts**: Fraunces (display serif), Inter (UI sans), Caveat (handwritten accents).
- **Design tokens** are defined as CSS custom properties at the top of the stylesheet (colors, radii, shadows), making it easy to retheme.
- **Animations** use pure CSS keyframes (blob morph, floating cards) plus an `IntersectionObserver` that adds an `.in` class to elements with `.reveal` as they scroll into view.
- **Interactivity**: FAQ accordion, mobile hamburger toggle, and a fake newsletter submit handler that flashes a success state on the button.

## File structure

```
.
├── index.html      # Entire site — markup, styles, and scripts
└── roju-logo.png   # Referenced by the nav and footer (not included)
```

The footer references `roju-logo.png` via a relative path, so that image needs to live next to `index.html` for the logo to render.

## Running it

Because everything is self-contained, you can just open the file:

```
open index.html
```

For local development with live reload, any static server works:

```
npx serve .
# or
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploying

Drop `index.html` (and `roju-logo.png`) onto any static host — GitHub Pages, Netlify, Vercel, Cloudflare Pages, S3, or even a plain shared host. No build, no environment variables.

## Things to customize before going live

- **Logo image** — add `roju-logo.png` (or update the `<img src>` paths).
- **Contact info** — the FAQ uses `hola@rojustudio.cr` and `+506 8543-2109`, while the final CTA and footer use `hola@rojustudio.com` and `+506 8888-8888`. Pick one set and make them consistent.
- **CTA buttons** — most `href="#"` links (booking, service pages, blog, careers, social icons) are placeholders.
- **Newsletter form** — `handleSubscribe()` only fakes success; wire it to a real provider (Mailchimp, ConvertKit, Buttondown, etc.).
- **Client logos** — currently styled text placeholders; swap in real marks when ready.
- **Copyright year** in the footer is hardcoded to 2026.

## Browser support

Modern evergreen browsers. Uses `backdrop-filter`, CSS custom properties, `aspect-ratio`, and `IntersectionObserver` — all widely supported in current Chrome, Safari, Firefox, and Edge.
