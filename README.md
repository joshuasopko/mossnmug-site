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
- [x] Add reCAPTCHA to contact form (Netlify's built-in reCAPTCHA 2, no keys needed)
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
AJAX submission — no page reload on success

Spam protection, in layers:
- Honeypot field `bot-field` (off-screen), checked by Netlify
- Netlify reCAPTCHA 2 (`data-netlify-recaptcha`), checked by Netlify. The checkbox is injected at deploy time, so it does not appear on localhost
- Netlify's built-in Akismet filter (caught messages land under Forms → Spam submissions in the Netlify dashboard)
- Client-side checks in `index.html`: too-fast submits, link stuffing, field length limits
- The contact email is assembled in script so it is not scrapeable from the page source
