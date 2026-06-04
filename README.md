# Moss & Mug — mossnmug.coffee

Single-page landing site for Moss & Mug, Herbal Coffee & Tea Bar.
Located inside Juniper Apothecary, Sioux Falls, SD.

## Stack
- Plain HTML/CSS/JS — no framework, no build step
- Netlify hosting + Netlify Forms (built-in spam honeypot)
- Custom domain: mossnmug.coffee (primary)
- Redirect: mossnmugcoffeeco.com → mossnmug.coffee

## Files
- `index.html` — entire site (single file)
- `netlify.toml` — Netlify config, redirect rules, security headers

## TODO before launch
- [ ] Add real street address in the Visit section
- [ ] Confirm hours are correct
- [ ] Replace map placeholder with Google Maps embed iframe
- [ ] Set up Cloudflare Email Routing: hello@mossnmug.coffee → personal Gmail
- [ ] Set Netlify form notification email to hello@mossnmug.coffee
- [ ] Add reCAPTCHA v3 to contact form (post-launch)
- [ ] Swap placeholder copy with final approved copy
- [ ] Add real photography when available (hero background, about section)

## Deploy steps (Claude Code)
1. Create new GitHub repo: mossnmug-site (separate from Allowance Lab)
2. Push this folder to main branch
3. Connect repo to Netlify
4. Add custom domain mossnmug.coffee in Netlify domain settings
5. Point mossnmug.coffee DNS to Netlify (via Cloudflare)
6. Set Netlify form submission notification to hello@mossnmug.coffee
7. Set up mossnmugcoffeeco.com as redirect domain in Netlify

## Netlify Forms
Form name: "contact" — Netlify auto-detects via data-netlify="true"
Honeypot field: bot-field (hidden, catches basic spam bots)
AJAX submission — no page reload on success
