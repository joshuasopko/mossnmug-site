# Moss & Mug — mossandmug.coffee

Single-page landing site for Moss & Mug, Herbal Coffee & Tea Bar.
Located inside Juniper Apothecary, Sioux Falls, SD.

## Stack
- Plain HTML/CSS/JS — no framework, no build step
- Netlify hosting + Netlify Forms (built-in spam honeypot)
- Custom domain: mossandmug.coffee (primary)

## Files
- `index.html` — entire site (single file: markup, styles, script)
- `img/` — photography (cropped and graded for web), `art.svg` line-art sprite, `og.jpg` share image
- `netlify.toml` — Netlify config, security headers

## TODO before launch
- [ ] Add real street address in the Visit section
- [ ] Confirm hours are correct
- [ ] Replace map placeholder with Google Maps embed iframe
- [x] Set up Cloudflare Email Routing: hello@mossandmug.coffee → personal Gmail
- [ ] Set Netlify form notification email to hello@mossandmug.coffee
- [ ] Add reCAPTCHA v3 to contact form (post-launch)
- [ ] Swap placeholder copy with final approved copy
- [x] Add real photography (hero, story, the bar, visit)

## Deploy steps (Claude Code)
1. Create new GitHub repo: mossnmug-site (separate from Allowance Lab)
2. Push this folder to main branch
3. Connect repo to Netlify
4. Add custom domain mossandmug.coffee in Netlify domain settings
5. Point mossandmug.coffee DNS to Netlify (via Cloudflare)
6. Set Netlify form submission notification to hello@mossandmug.coffee

## Netlify Forms
Form name: "contact" — Netlify auto-detects via data-netlify="true"
Honeypot field: bot-field (hidden, catches basic spam bots)
AJAX submission — no page reload on success
