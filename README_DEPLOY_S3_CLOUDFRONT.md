# IRSG + regPulse — Static Site (AWS S3 + CloudFront)
This package contains a production-ready static website:
- `index.html` (home / IRSG consulting) — includes a slide-in program widget on the hero right column
- `regpulse.html` (product page with features, tiers, and demo form)
- `assets/css/style.css` (brand palette: blue/green/white)
- `assets/img/logo.gif` (your uploaded logo)
- `assets/img/screenshots/*.png` (placeholder screenshots)

## Quick deploy to S3
1. Create an S3 bucket (e.g., `irsg-site-prod`) with **Block Public Access: OFF** for static hosting, or leave ON if you serve via CloudFront OAI.
2. Upload *all* files in this folder preserving structure.
3. If using S3 static website hosting directly, enable **Static website hosting** and set `index.html` as Index document.

### Recommended: CloudFront in front of S3
1. Create a CloudFront distribution with the S3 bucket as the origin.
2. If using OAC (Origin Access Control), keep the bucket private and attach the generated bucket policy from AWS.
3. Set default root object to `index.html`.
4. Add behavior to support SPA-like paths if needed (not required here).

## Cache headers
- `/assets/*` → `Cache-Control: public,max-age=2592000` (30 days)
- `*.html` → `Cache-Control: public,max-age=300` (5 minutes)

## Forms (static site)
Replace the `form action="#"` with Formspree, Basin, Netlify Forms, or your own API gateway.

## Customization
- Colors and spacing live in `assets/css/style.css`.
- Replace placeholder screenshots in `assets/img/screenshots/` with real product images.
- Update footer/contact info in both HTML files.

## Local preview
Open `index.html` in a browser. Navigate to `regpulse.html` for the product page.
