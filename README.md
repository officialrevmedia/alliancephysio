# Alliance Physio Website

Production-ready website for Alliance Physio in Meadowvale, Mississauga.
Built as a static site, optimized for SEO, ready to deploy to GitHub Pages.

## Quick Start

### Option A: Deploy to GitHub Pages

1. **Create a GitHub repository** (e.g. `alliancephysio.github.io` for a user/org site, or any name for a project site).

2. **Push these files to the repository:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Repository -> Settings -> Pages
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)`
   - Save

4. **Custom domain** (optional but recommended):
   - Edit the `CNAME` file to contain your domain (e.g. `alliancephysio.com`)
   - In Settings -> Pages, add your custom domain
   - In your DNS provider, add either:
     - **A records** pointing to GitHub's IPs:
       - `185.199.108.153`
       - `185.199.109.153`
       - `185.199.110.153`
       - `185.199.111.153`
     - **CNAME record** for `www`: `YOUR-USERNAME.github.io`
   - Enable "Enforce HTTPS" once DNS propagates

### Option B: Deploy to any static host (Netlify, Vercel, Cloudflare Pages)

Just drag-and-drop this folder onto Netlify Drop, or connect your GitHub repo. No build step required - everything is pre-built.

## Optimized for Performance

This site is pre-optimized for fast loading and easy deployment:
- All images compressed to web-optimal sizes (JPEG progressive, quality 82)
- Team photos: max 800px wide
- Service photos: max 1200px wide
- Hero image: max 1800px wide
- Total payload: ~6 MB (most pages load in under 1 second)
- All CSS inline, no external dependencies except Google Fonts
- All images use `loading="lazy"` for fast initial paint
- Logo: vector-quality PNG with transparent background

If you need higher-resolution images (e.g. for print or marketing), keep the originals separately - the web versions are intentionally compressed.

## Site Structure

```
/
├── index.html                  Home page (Alliance Physio Mississauga)
├── about/index.html            About page with team
├── services/
│   ├── index.html              Services overview
│   ├── physiotherapy/index.html
│   ├── sports-medicine/index.html
│   ├── clinical-reformer-pilates/index.html
│   ├── registered-massage-therapy/index.html
│   ├── chiropractic/index.html
│   ├── osteopathy/index.html
│   ├── acupuncture/index.html
│   ├── concussion-program/index.html
│   ├── shockwave-therapy/index.html
│   ├── spinal-decompression/index.html
│   ├── custom-orthotics/index.html
│   ├── naturopath/index.html
│   ├── dry-needling/index.html
│   ├── bracing-orthopedic-products/index.html
│   └── compression-stockings/index.html
├── conditions/index.html       Conditions we treat
├── contact/index.html          Contact + JaneApp booking
├── 404.html                    Custom 404 page
├── sitemap.xml                 SEO sitemap (auto-discovered by search engines)
├── robots.txt                  Crawler guidance
├── _config.yml                 Jekyll config (for GitHub Pages plugins)
├── .nojekyll                   Tells GitHub Pages to skip Jekyll processing of HTML
├── CNAME                       Custom domain (edit me)
├── FINAL_patient_handout.pdf   Sports Medicine handout
└── assets/
    ├── logo-dark.png           Navy logo (for white header)
    ├── logo-white.png          White logo (for dark footer)
    ├── logo.png                Original logo (kept as backup)
    ├── hero.jpg                Home hero image
    ├── team/                   14 practitioner headshots
    ├── services/               15 service photos
    └── sections/               4 section / spotlight photos
```

## SEO Features

- **Unique title and meta description on every page** targeting local Mississauga keywords
- **Canonical URLs** to prevent duplicate-content issues
- **Open Graph + Twitter Card tags** for social sharing previews
- **Schema.org structured data** (MedicalClinic + BreadcrumbList) on every page
- **sitemap.xml** auto-discoverable at `/sitemap.xml`
- **robots.txt** with proper directives at `/robots.txt`
- **Geo meta tags** for local SEO (Mississauga / Meadowvale)
- **Mobile-first responsive design** (Google ranks mobile-first)
- **Fast loading** - all CSS inline, all images lazy-loaded
- **Pretty URLs** (no `.html` extensions in the URL bar)

## Updating Content

The HTML is hand-written and well-organized. To make edits:

1. **Text edits:** Open the relevant `index.html` file in any editor and edit directly.
2. **Image swaps:** Drop replacement files into `assets/services/` or `assets/team/` keeping the same filename, or update the `<img src>` references.
3. **Adding a new service:** Copy any existing service folder under `/services/`, rename, and edit the content + nav links.
4. **Team changes:** Edit `/about/index.html` and update the team grid.

## Post-Launch Checklist

After deploying:

- [ ] **Google Search Console** - Add property at https://search.google.com/search-console, verify ownership, submit `sitemap.xml`
- [ ] **Bing Webmaster Tools** - Submit at https://www.bing.com/webmasters
- [ ] **Google Business Profile** - Verify and link to your new domain
- [ ] **Schema validation** - Test pages at https://search.google.com/test/rich-results
- [ ] **Page speed test** - https://pagespeed.web.dev/
- [ ] **Mobile-friendly test** - https://search.google.com/test/mobile-friendly
- [ ] **Update JaneApp** - Ensure all booking links still resolve correctly
- [ ] **301 redirects** - If you had old URLs, set up redirects from old to new structure

## Tech Notes

- Pure static HTML / CSS / JS, no build pipeline needed
- All pages share the same header, footer, and design system
- Each page is self-contained with its own SEO metadata
- Internal links use real URLs (good for crawlers) instead of SPA routing
- `.nojekyll` prevents GitHub Pages from re-processing the pre-built HTML

## Contact

For questions about this site or to make significant changes, contact your developer.

Built for Alliance Physio - Meadowvale, Mississauga.
