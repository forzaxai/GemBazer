# GemBazar

A single-page, self-contained website template for a game top-up / digital-services marketplace (Free Fire diamonds, PUBG Mobile UC, social media boosts) styled for a Bangladeshi audience — bKash / Nagad / Rocket payment badges, BDT pricing, gamer-dark visual theme.

This is an **original design** — its own name, logo mark, copy, and layout — built as a template you can brand as your own. It is not a copy of any existing business's site, name, or account handles.

Everything lives in one file: `index.html`. No build step, no dependencies to install — just HTML, CSS, and vanilla JS (Google Fonts loaded via CDN link).

## Preview locally

Just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## What's included

- **`index.html`** — the public storefront: responsive hero, category grid, filterable product grid, "how it works" steps, features, and a support banner. Client-side category filter, mobile nav, scroll-reveal animations, `prefers-reduced-motion` support.
- **`admin.html`** — a local admin panel for managing the catalog and logging orders (details below).

## The admin panel (`admin.html`)

Open `admin.html` directly in a browser (not linked from the public storefront nav on purpose). Default passcode: **`gembazar2026`** — change it immediately (see below).

**What it does:**
- **Dashboard** — quick counts of products and orders.
- **Products** — add/edit/delete top-up packages, with a live preview card. A **"Copy grid HTML"** button generates the exact markup for `index.html`'s `#product-grid`, so you paste it in and commit to publish changes. A **"Download products.json"** button exports a backup.
- **Orders** — a manual log for orders you take over Telegram/WhatsApp: customer contact, product, amount, and a Pending/Delivered status you can toggle.
- **Settings** — explains the panel's limits and lets you reset back to the seed data.

**Important limits — please read before relying on this:**
- **No backend, no database.** This is a static site. Everything in the admin panel lives in the browser tab's memory only — it **resets the moment you refresh or close the page**. It's meant for drafting catalog edits and jotting down orders you're already handling manually, not as a system of record.
- **The passcode is not real security.** It's a plain constant (`ADMIN_PASSCODE`) inside `admin.html`'s source code. Since GitHub repos and GitHub Pages sites are public, anyone can view the page source and read it. Treat the login as a casual deterrent against people stumbling onto the page, not as access control for anything sensitive.
- **If you need real persistence or real security** — a shared order history across devices/teammates, or a login that can't be read from the page source — that requires an actual backend (a small server + database, or a service like Airtable/Google Sheets/Supabase behind a form). Happy to help wire one up if/when you're ready for that.

## Before you launch — replace these placeholders

- **Brand name & logo**: currently "GemBazar" with a custom SVG gem mark in `<symbol id="gem-icon">`
- **Prices**: all product prices are sample figures — swap in your real pricing
- **Contact links**: the Telegram (`t.me/yourbrand`) and WhatsApp (`wa.me/8800000000`) links in the support section are placeholders
- **"Top Up Now" buttons**: currently scroll to the support section — wire these up to your real checkout/order flow once you have one (this template has no backend or payment integration)
- **Login / Register buttons**: currently link to `#` — connect to your actual auth pages
- **Footer legal links** (Terms, Privacy, FAQ): currently placeholders

## Publish it on GitHub

1. Create a new repository on GitHub (e.g. `gembazar`).
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. **To host it live with GitHub Pages**: go to your repo's **Settings → Pages**, set Source to your `main` branch and `/ (root)`, and save. Your site will be live at `https://<your-username>.github.io/<your-repo>/` within a minute or two.
