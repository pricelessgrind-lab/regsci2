
# IRSG + regPulse — GitHub Pages Package

This folder is ready to publish via GitHub Pages.

## Option A — Pages from `main` (no workflow)
1. Create a new repo on GitHub (public or private with Pages enabled).
2. Upload these files to the repo **root** (index.html should be at the top level).
3. (Optional) Edit `CNAME` to your custom domain or delete it if you won't use one.
4. Go to **Settings → Pages**:
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)`
5. Wait for Pages to build and open the site URL.

## Option B — Use `gh-pages` branch via GitHub Actions (automated)
- Keep your source in `/src` (not included here) and deploy the built site in `gh-pages`.
- This package already includes a workflow: `.github/workflows/pages.yml`.
- Steps:
  1. Commit everything to the repository (on `main`).
  2. Push to GitHub.
  3. The workflow will publish the `./` folder to the `gh-pages` branch.
  4. In **Settings → Pages**, select `Deploy from a branch`, choose `gh-pages` and `/ (root)`.

## Forms
This is a static site. Replace the `form action="#"` with Formspree, Basin, Netlify Forms, or your own API endpoint.

## Custom Domain
- Keep the `CNAME` file at the repo root containing only your domain (e.g., `example.com`).
- Point your DNS to GitHub Pages:
  - Apex: A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  - `www` subdomain: CNAME to `YOUR-USERNAME.github.io`
