# Alliance Physio Website - Final Deployment Guide

## What's In This Package

This is the final, fully-tested website package for Alliance Physio. Everything has been audited and verified.

**Verified working:**
- 20 indexable pages with unique SEO metadata
- All 14 team headshots and 15 service photos
- Hero image properly centered
- Working conditions page filter (tabs + search)
- Contact form opens email with pre-filled content
- Sports Medicine page with patient handout PDF link and Find My Treatment decision tree
- Footer credit reads "Created by revmedia.ca" on all pages
- No em-dashes, no broken links, no placeholder text
- All SEO titles under 70 characters (Google-optimized)
- Schema.org structured data on every page
- Sitemap, robots.txt, custom domain (CNAME) all configured for mississaugaphysio.ca

---

## Deployment Steps (Clean Re-Upload)

### Step 1: Delete everything in your repo

Go to `https://github.com/officialrevmedia/alliancephysio`

**Quick wipe method:**
1. While on the repo page, press the **`.` (period) key** on your keyboard
2. VS Code opens in your browser at github.dev
3. In the left sidebar, right-click each file or folder → **Delete**
4. Click the **Source Control** icon (branching tree icon)
5. Type a commit message: `Clean wipe for fresh deploy`
6. Click the **Commit & Push** button (checkmark icon)
7. Close the github.dev tab

---

### Step 2: Prepare files on your computer

1. Download `alliance-physio-website.zip`
2. **Unzip it:**
   - Mac: double-click
   - Windows: right-click → Extract All
3. You'll get a folder called `alliance-physio-website`

**Show hidden files (CRITICAL):**
- **Mac:** In Finder, press `Cmd + Shift + .` (period key)
- **Windows:** File Explorer → View tab → check "Hidden items"

You should now see `.nojekyll` and `.gitignore` in the folder listing.

---

### Step 3: Upload using Chrome or Edge

**Do NOT use Safari or Firefox** — they break folder uploads.

1. Go back to your empty repo
2. Click **uploading an existing file** (or **Add file → Upload files**)
3. Open the unzipped `alliance-physio-website` folder on your computer
4. Inside it, select everything: `Cmd+A` (Mac) or `Ctrl+A` (Windows)
5. Drag the entire selection into GitHub's upload area

**In the upload preview, verify you see:**
- `.nojekyll` (a file, no extension)
- `index.html`
- `about/index.html`
- `services/physiotherapy/index.html` (slashes confirm folders preserved)
- `assets/team/lisa.jpg`

If the slashes aren't there → folder structure isn't being preserved → try a different browser.

6. Scroll down
7. Commit message: `Final website deploy`
8. Click **Commit changes**

Upload takes 1-3 minutes.

---

### Step 4: Verify deployment

1. Click the **Actions** tab in your repo
2. Wait for the green checkmark on "pages build and deployment"
3. Once green, open `https://mississaugaphysio.ca/` **in an incognito/private window**:
   - Mac Chrome: `Cmd+Shift+N`
   - Windows Chrome/Edge: `Ctrl+Shift+N`
   - Safari: `Cmd+Shift+N`

---

## Verification Checklist

After deploying, test each item:

### Home page
- [ ] Light blue color scheme with white background
- [ ] Large serif heading "Restore movement. Rebuild strength."
- [ ] Hero image of woman stretching on the right side
- [ ] Woman centered in her frame (not pushed to one edge)
- [ ] Trust bar shows: 15+ Practitioners, 40k+ Patient Visits, Open Mon-Sat, Since 2009
- [ ] Services carousel works (arrows or scroll)
- [ ] Dr. Amin spotlight section displays
- [ ] Footer reads "Created by **revmedia.ca**"

### About page (`/about/`)
- [ ] All 14 team member photos display
- [ ] First member listed: "Lisa Duong Agatep" (full name)
- [ ] NO "Practitioner bios shown above are draft placeholders" text at bottom
- [ ] Page sections: Our Story, Our Values, Meet the Team

### Conditions page (`/conditions/`)
- [ ] Hero with photo on right side
- [ ] Stats row shows: 33+ Conditions, 8 Body Regions, 15+ Practitioners
- [ ] Sticky filter bar with search box and pill-style tabs
- [ ] Click "Neck & Head" tab → only neck/head conditions show
- [ ] Click "Knee" tab → only knee conditions show
- [ ] Type "back" in search → filters everything to back-related matches
- [ ] Click "All Regions" → everything reappears

### Contact page (`/contact/`)
- [ ] Form has fields: First Name, Last Name, Email, Phone, Service, Message
- [ ] Fill in first name, last name, email, and message
- [ ] Click "Send Message" button
- [ ] Your default email app opens (Apple Mail, Outlook, etc.)
- [ ] Email is addressed to: alliancephysiowellness@gmail.com
- [ ] Subject and body are pre-filled with your details

### Sports Medicine page (`/services/sports-medicine/`)
- [ ] Page loads without 404
- [ ] Family physician referral notice prominent
- [ ] "Download Patient Handout PDF" button works
- [ ] Find My Treatment decision tree (Start Over button)
- [ ] Injection therapy tabs (Joint / Soft Tissue / Shoulder)

### All other service pages
- [ ] Each loads with hero image, content, FAQ, and CTA
- [ ] All 15 service pages accessible from the Services dropdown menu

---

## Common Issues and Fixes

**Symptom: Site shows plain text with `canonical: ...` at the top**
→ Jekyll is processing the HTML. The `.nojekyll` file is missing or wrong.
→ Fix: In repo, click **Add file → Create new file**, type `.nojekyll` exactly (no extension, no trailing period), leave body empty, commit.

**Symptom: Some service pages 404**
→ A folder got skipped during upload.
→ Fix: Check that `services/` folder has all 15 subfolders. Re-upload missing ones.

**Symptom: Images broken on sub-pages but work on home**
→ Old relative paths from a previous upload still cached.
→ Fix: Clear browser cache or test in incognito window.

**Symptom: Conditions tabs don't filter**
→ JavaScript is being blocked by Jekyll.
→ Fix: Verify `.nojekyll` exists (see first symptom above).

**Symptom: GitHub Pages says "Page build failed"**
→ Check the Actions tab for the error. Most common: file too large.
→ This package is 6.2 MB total - well under any limits.

---

## SEO Setup (Post-Launch)

After the site is live:

1. **Google Search Console:** https://search.google.com/search-console
   - Add property: `mississaugaphysio.ca`
   - Verify ownership (HTML tag method)
   - Submit sitemap: `https://mississaugaphysio.ca/sitemap.xml`

2. **Google Business Profile:**
   - Update the listing to point to `https://mississaugaphysio.ca/`
   - Verify all hours, phone, and address match the website

3. **Bing Webmaster Tools:** https://www.bing.com/webmasters
   - Add property, submit sitemap

4. **Schema validation:** https://search.google.com/test/rich-results
   - Test the home page URL — should detect MedicalClinic + BreadcrumbList

5. **Performance test:** https://pagespeed.web.dev/
   - Should score 90+ on Mobile and Desktop

---

## Site Structure

```
alliance-physio-website/
├── .github/                              GitHub Actions workflow (optional, not used)
├── .nojekyll                             CRITICAL - disables Jekyll processing
├── .gitignore                            Standard exclusions
├── 404.html                              Custom 404 error page
├── CNAME                                 Custom domain: mississaugaphysio.ca
├── FINAL_patient_handout.pdf             Sports Medicine handout PDF
├── README.md                             This file
├── index.html                            Home page
├── robots.txt                            Search engine directives
├── sitemap.xml                           SEO sitemap (20 URLs)
├── about/index.html                      About page with team
├── conditions/index.html                 Conditions page (filtered grid)
├── contact/index.html                    Contact page (form + map)
├── assets/
│   ├── hero.jpg                          Home hero image
│   ├── logo-dark.png                     Navy logo (for white header)
│   ├── logo-white.png                    White logo (for dark footer)
│   ├── sections/                         4 section photos
│   ├── services/                         15 service photos
│   └── team/                             14 practitioner headshots
└── services/
    ├── index.html                        Services overview
    ├── acupuncture/index.html
    ├── bracing-orthopedic-products/index.html
    ├── chiropractic/index.html
    ├── clinical-reformer-pilates/index.html
    ├── compression-stockings/index.html
    ├── concussion-program/index.html
    ├── custom-orthotics/index.html
    ├── dry-needling/index.html
    ├── naturopath/index.html
    ├── osteopathy/index.html
    ├── physiotherapy/index.html
    ├── registered-massage-therapy/index.html
    ├── shockwave-therapy/index.html
    ├── spinal-decompression/index.html
    └── sports-medicine/index.html
```

Total: **20 indexable pages**, **34 images**, **6.2 MB**

Built for Alliance Physio - Meadowvale, Mississauga.
