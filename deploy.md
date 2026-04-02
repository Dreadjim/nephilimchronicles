# Nephilim Chronicles — Deploy Guide

Everything you need to get this live on your domain in under 30 minutes.

---

## Step 1 — Get your domain

**Recommended domain:** `nephilimchronicles.com`

Buy it from one of these registrars (all roughly $10–15/year):
- **Namecheap** → namecheap.com (usually cheapest, good interface)
- **Cloudflare Registrar** → cloudflare.com/products/registrar (at-cost pricing, no markup)
- **GoDaddy** → godaddy.com (most popular, slightly pricier)

Search for: `nephilimchronicles.com`
Backup options if taken:
- `thenephilimchronicles.com`
- `nephilimcodex.com`
- `nephilim-chronicles.com`

---

## Step 2 — Set up your free email list (Formspree)

The waitlist form is wired up and ready — you just need your free Formspree ID.

1. Go to **formspree.io** and sign up (free — 50 submissions/month)
2. Click **"New Form"**
3. Name it "Nephilim Chronicles Waitlist"
4. Copy your form ID — it looks like: `xeqkbyza`
5. Open `index.html` in any text editor
6. Find this line (near the bottom, in the `<form>` tag):
   ```
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
7. Replace `YOUR_FORM_ID` with your actual ID, e.g.:
   ```
   action="https://formspree.io/f/xeqkbyza"
   ```
8. Save the file

**Free tier:** 50 submissions/month
**Upgrade:** $10/month for unlimited

---

## Step 3 — Deploy to Netlify (FREE — drag and drop)

Netlify is the fastest way to get this live. Free plan covers everything you need.

1. Go to **app.netlify.com** and sign up (free)
2. Click **"Add new site"** → **"Deploy manually"**
3. Drag the entire `nephilim-site` folder onto the drop zone
4. Netlify will give you a URL like: `magical-name-123.netlify.app`
5. Your site is now live on the internet!

**To connect your domain:**
1. In Netlify dashboard → go to your site → **"Domain settings"**
2. Click **"Add custom domain"** → type `nephilimchronicles.com`
3. Netlify will give you DNS records (nameservers or CNAME/A records)
4. Go to your domain registrar and update the DNS to point to Netlify
5. Wait 15–60 minutes for DNS to propagate
6. Done — your site is live at `nephilimchronicles.com`

Netlify also automatically handles:
- HTTPS / SSL certificate (free)
- CDN (global fast loading)
- Form handling (optional alternative to Formspree)

---

## Step 4 — Update SEO settings

Once you have your real domain, do a find-and-replace in `index.html`:

Replace all instances of:
```
https://nephilimchronicles.com
```
With your actual domain, e.g.:
```
https://nephilimchronicles.com
```
(If that IS your domain, nothing to change. Otherwise swap accordingly.)

---

## Step 5 — Set up Google Search Console

This is how you tell Google your site exists and monitor rankings.

1. Go to **search.google.com/search-console**
2. Sign in with a Google account
3. Click **"Add Property"** → enter your domain
4. Verify ownership by adding a DNS TXT record (Netlify makes this easy)
5. Submit your sitemap: click **"Sitemaps"** → enter `sitemap.xml` → Submit
6. Check back in 3–7 days to see which queries Google found you for

---

## Step 6 — Add your real images

Replace placeholder images with your actual art:
- Open `index.html` in any text editor
- Search for `src="images/` to find the local image tags
- Replace with your uploaded image files (drop them in the `images/` folder)
- For creature cards, search for `src="https://images.unsplash.com` and replace with your own art

Your images folder is at: `nephilim-site/images/`

---

## File Structure

```
nephilim-site/
├── index.html          ← Main site (edit this for all content changes)
├── sitemap.xml         ← Update URLs to your real domain
├── robots.txt          ← Update sitemap URL to your real domain
├── DEPLOY.md           ← This file
└── images/
    ├── azazel-hero.png    ← Azazel hero image
    └── samyaza-hero.png   ← Samyaza hero image
```

---

## Editing the site

Everything is in `index.html`. It's divided into clear sections:

- **Hero copy** → search for `hero-title`, `hero-desc`, `hero-clarity`
- **Features section** → search for `feature-card`
- **Azazel entry** → search for `featured-content`
- **Creature cards** → search for `creature-card`
- **Roadmap** → search for `phase-item`
- **FAQ** → search for `faq-item`
- **Waitlist** → search for `join-benefit`
- **Footer** → search for `footer`

Use any text editor — VS Code (free) is the best option.

---

## Future Phases (SEO expansion)

Once the site is live, the biggest SEO unlock is adding dedicated pages:

```
/what-are-the-nephilim
/watchers-book-of-enoch
/who-is-azazel
/biblical-giants
/codex/azazel
/codex/samyaza
/codex/rephaim
```

Each page targets a major keyword cluster that people actually search for.
This is what transforms the site from "branded presence" to "search capture machine."

---

## Questions?

Everything is plain HTML/CSS/JavaScript — no framework, no build step, no database required.
You can open `index.html` directly in any browser to preview it before deploying.
