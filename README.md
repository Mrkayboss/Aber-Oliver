# Willow & Wren Midwifery Care — Website Prototype

A working, responsive one-page website prototype for a midwife/nursing
practice. Plain HTML/CSS/JS — no build step, no dependencies to install.

## Files
```
midwife-site/
├── index.html    # all page content and structure
├── styles.css    # design system (colors, type, layout, responsive rules)
├── script.js     # mobile nav, scroll animations, contact form handler
└── README.md
```

## How to run it

**Easiest:** double-click `index.html` — it opens directly in your browser.

**Recommended (avoids some browser quirks):** serve it locally.
```bash
cd midwife-site
python3 -m http.server 8000
# then open http://localhost:8000
```
or, with Node installed:
```bash
npx serve .
```

## How to deploy it

Any static host works, in order of ease:

- **Netlify** — drag the `midwife-site` folder onto [app.netlify.com/drop](https://app.netlify.com/drop). Live in seconds, and it's also the easiest way to wire up the contact form (see below).
- **Vercel** — `npx vercel` from inside the folder.
- **GitHub Pages** — push the folder to a repo, enable Pages on the `main` branch.

## Connecting the contact form

Right now the form works client-side (validates, shows a confirmation
message) but doesn't send anywhere — that needs a backend. Pick one:

1. **Netlify Forms** (if hosting on Netlify): add `data-netlify="true"` and
   a hidden `form-name` input to the `<form>` tag. No JS changes needed.
2. **Formspree**: create a free form at formspree.io, then change the
   `<form>` tag's behavior to POST to your Formspree endpoint instead of
   using `script.js`'s `preventDefault()` handler.
3. **EmailJS**: keep the JS-driven submit, but call `emailjs.send(...)`
   inside the `submit` handler in `script.js` instead of just showing the
   status message.

## What to extend first

Roughly in priority order:

1. **Real content & photos** — swap the placeholder bio, credentials, and
   gallery gradient tiles for the actual midwife's photo, real
   certifications, and real practice photos.
2. **Wire up the contact form** — pick one option above so inquiries
   actually arrive somewhere (email/inbox).
3. **Booking** — embed a Calendly (or similar) widget in the hero and
   contact section so "Book a Consultation" leads to an actual calendar,
   not just a scroll-to-form.
4. **Real social links** — the header/footer/contact icons currently point
   to `#`; swap in the practice's actual Facebook, Instagram, TikTok,
   YouTube, Pinterest, and WhatsApp (click-to-chat: `https://wa.me/<number>`) URLs.
5. **Google Map embed** — replace the dashed placeholder box in Contact
   with a real `<iframe>` Google Maps embed for the office address.
6. **Split into multiple pages** — this prototype is a single scrolling
   page for speed of review. For SEO and a more traditional feel, split
   `index.html` into `about.html`, `services.html`, `contact.html`, etc.,
   duplicating the header/footer across each.
7. **SEO & analytics** — add per-page `<title>`/`<meta description>` (if
   split into multiple pages), a `sitemap.xml`, a favicon, and a Google
   Analytics or Plausible snippet.
8. **Blog/resources section** — if the midwife wants to publish articles,
   this is the next content type to add; likely worth a simple static-site
   generator (e.g. Eleventy) at that point rather than hand-written HTML.

## Design notes

- Palette: sage green + dusty rose + warm ivory, meant to read calm and
  trustworthy without falling into a "generic AI landing page" clay/cream
  look.
- Type: Fraunces (serif, warm) for headings, Karla (sans) for body text —
  loaded from Google Fonts via CDN in `index.html`.
- The dashed horizontal line through the Services section is a genuine
  sequence — it marks the four real stages of care (Prenatal → Labor &
  Birth → Postpartum → Ongoing Nursing Care) — rather than a decorative
  numbered list.
- All icons are inline SVG, so there's no icon-font dependency to load.
"# Aber-Oliver" 
"# Aber-Oliver" 
