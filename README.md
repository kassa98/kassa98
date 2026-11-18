# Ejesira Design Studio — website

A complete, self-contained website for Ejesira Design Studio, Addis Ababa.
No build step, no framework, no server-side code. Plain HTML, CSS and
JavaScript, so it will run on any host and keep working for years.

---

## 1. What is in this folder

```
index.html                 Home
about.html                 About the studio and the founder
collections.html           All pieces + the seven collections
design-development.html    Design & development services
portfolio.html             Project stories and the studio archive
journal.html               Journal / editorial
contact.html               Enquiry form and studio details
studio-editor.html         Your private content editor (not indexed)

robots.txt                 Search-engine instructions
sitemap.xml                Page list for Google

assets/css/site.css        All styling
assets/js/content.js       ALL EDITABLE CONTENT — the only file you change
assets/js/site.js          Site behaviour (navigation, galleries, form)
assets/img/                All photography
```

---

## 2. How to update the website

Everything you will ever want to change lives in **`assets/js/content.js`** —
studio details, products, collections, projects and journal entries.
The pages read from it, so one edit updates the whole site.

### The easy way — Studio Editor

1. Open **`studio-editor.html`** in your browser.
2. Edit anything: studio details, products, collections, projects, journal.
3. Click **Preview changes** to see the site with your edits before committing.
4. Click **Download content.js**.
5. Upload that file to your host, replacing `assets/js/content.js`.

### The direct way

Open `assets/js/content.js` in any text editor (Notepad is fine) and change
the text between the quote marks. Save, upload, done.

### Adding a new photograph

1. Save the image as a `.jpg`, about 1100 × 1100 pixels for a product.
2. Upload it into `assets/img/`.
3. Put its filename into the `img:` field of a product, project or journal entry.

**For product photographs**, shoot against a plain white wall or card in soft
daylight, with the shoe filling most of the frame. The site places every
product on a white card, so a white background blends invisibly.

---

## 3. Making the enquiry form deliver to your inbox

Right now the form opens the visitor's own email app with their message
already written. That works everywhere and costs nothing.

To have enquiries arrive in your inbox automatically:

1. Create a free form endpoint at **formspree.io**, **basin.com** or **getform.io**.
2. They give you a URL that looks like `https://formspree.io/f/xxxxxxx`.
3. Paste it into the `formEndpoint` field — in Studio Editor under *Contact form*,
   or in `content.js` under `studio: { ... formEndpoint: "" }`.

---

## 4. Putting the site online

Any static host works. All three of these are free for a site this size:

### Netlify (simplest)
1. Go to **app.netlify.com/drop**
2. Drag this whole folder onto the page.
3. It is live in about ten seconds on a `*.netlify.app` address.
4. *Site settings → Domain management* to connect `ejesira.com` or similar.

### Cloudflare Pages
1. **pages.cloudflare.com** → *Create a project* → *Direct upload*.
2. Upload this folder. Connect your domain under *Custom domains*.

### Ordinary web hosting (cPanel, Ethiopian hosts, etc.)
Upload the entire contents of this folder into `public_html/` by FTP.
`index.html` must sit at the top level.

### After it is live
1. Edit `sitemap.xml` and `robots.txt`, replacing `https://ejesira.design/`
   with your real domain.
2. Do the same for the `<link rel="canonical">` line in the `<head>` of each page.
3. Submit your domain to **search.google.com/search-console**.

---

## 5. Things left deliberately blank

These are empty because the information has not been confirmed. The site hides
empty fields rather than showing invented ones.

| Item | Where to fill it in |
|---|---|
| Instagram, Facebook, LinkedIn, TikTok links | `studio.social` in `content.js` |
| Contact-form endpoint | `studio.formEndpoint` |
| Prices, sizes, stock levels | Not published anywhere — confirmed per enquiry |

**Prices and shopping cart.** The site is built so that e-commerce can be added
later without redesigning anything: each product is already a structured record
with its own ID. Live payments need a payment provider account (Telebirr,
Chapa, Stripe) and a host that can run server code — tell me when you have
those and the catalogue can be switched on.

---

## 6. Where the photographs came from

Every image on this site is your own work, taken from:

- `EJESIRA_DESIGN_STUDIO_LOOKBOOK_2026_DIGITAL.pdf` — product photography
- `Ejesira_Design_Studio_KARAKTA2026_Concept_Sketchbook_V01.pdf` — sketches
- `Ejesira Design Studio interior/` — the atelier photographs
- `ejesira logo.png` — the registered Amharic mark, used in the footer

Product photographs were cut out of the lookbook plates, had their backgrounds
removed, and were placed on identical white cards so the grid reads as one
consistent set.

**Nothing was used from `F:\01_FOOTWEAR`, `F:\02_LEATHER_GOODS` or
`F:\03_DESIGN_TECHNICAL\Sketches`.** Those folders are trend and reference
libraries — screenshots from Instagram and Pinterest, and catalogue pages from
other brands. Publishing them as Ejesira products would be inaccurate and would
risk a copyright complaint.

---

## 7. Technical notes

- **Responsive** — tested at 1440 px desktop and 390 px mobile.
- **Accessible** — skip link, keyboard-operable menu and lightbox, visible focus
  rings, alt text on every image, `prefers-reduced-motion` respected.
- **SEO** — unique titles and meta descriptions, canonical URLs, Open Graph and
  Twitter cards, JSON-LD structured data (LocalBusiness, Service, CollectionPage,
  ContactPage, Blog), sitemap and robots.txt.
- **Performance** — total page weight is small; images are progressive JPEGs,
  lazy-loaded below the fold, with the hero preloaded.
- **Fonts** — Cormorant Garamond and Inter from Google Fonts, with Georgia and
  Helvetica fallbacks so the site still looks right if the fonts fail to load.
- **Browsers** — current Chrome, Safari, Firefox and Edge, desktop and mobile.

### Running it on your own computer

Double-clicking `index.html` works. If anything looks wrong, run a tiny local
server instead — from this folder:

```
python -m http.server 8000
```

then open `http://localhost:8000`.

---

## 8. Quality assurance performed

| Check | Result |
|---|---|
| Every internal link resolves | Pass — no broken links |
| Every referenced image exists | Pass — no missing files |
| Every `<img>` has alt text | Pass |
| JavaScript syntax (all three files) | Pass |
| Browser console errors, all 8 pages | None |
| Page render, desktop 1440 px | Pass — all 8 pages |
| Page render, mobile 390 px | Pass — all 8 pages |
| Title, meta description, canonical per page | Pass |
| Product images visually consistent | Pass — one piece removed for an unclean cutout |

---

*Ejesira Design Studio — Step forward, sustainably.*
