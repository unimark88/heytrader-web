# HeyTrader.io — Marketing Site

Landing page for HeyTrader.io. Static HTML/CSS/JS — no build step required.

## Structure

```
heytrader-web/
├── index.html          # the landing page
├── images/             # all section images (swap any PNG to change artwork)
│   ├── mission.png
│   ├── why-us.png
│   ├── assets.png
│   ├── how-it-works.png
│   ├── referral.png
│   ├── partners.png
│   ├── trust.png
│   └── src/            # editable SVG sources for every PNG
└── README.md
```

## Editing images

Every image has an editable SVG source in `images/src/`. To update one:
1. Edit the `.svg` in Figma, Illustrator, or any text editor
2. Re-export as PNG at 2x size, overwrite the file in `images/`
3. Or just drop in your own PNG with the same filename — nothing else changes

## Deploy (GitHub + Vercel)

1. Create a GitHub repo (e.g. `heytrader-web`), push these files to `main`
2. In Vercel: **Add New Project → Import** the repo → Framework preset: **Other** → Deploy
3. In Vercel project settings → **Domains**: add `heytrader.io` and `www.heytrader.io`
4. At your DNS provider: point `heytrader.io` (A record → 76.76.21.21) and
   `www` (CNAME → cname.vercel-dns.com) per Vercel's instructions
5. `app.heytrader.io`: create a CNAME pointing to the endpoint Match-Trader
   provides — the trading platform is entirely theirs, separate from this repo

Alternative: GitHub Pages (Settings → Pages → deploy from `main`) works too,
but Vercel makes the later Next.js upgrade seamless.

## Before going live — required

Replace every gold `[PLACEHOLDER]` in index.html:
- `[LEGAL ENTITY NAME]` — the licensed operating company
- `[COMPANY REG NO.]` — company registration number
- `[XXXXX]` — FSCA FSP number (verifiable at fsca.co.za)
- `[REGISTERED ADDRESS]`
- `[RESTRICTED JURISDICTIONS]` — per compliance advice

Also required before launch: real Risk Disclosure, Terms of Business,
Privacy and AML policy pages (footer links currently point to `#`).
Do not deploy to the live domain with placeholders in place.
