# English Students' Society — Jekyll Site

Full Jekyll site for the ESS at the University of Lethbridge.  
Adapted from the Wix site at essclubuleth.wixsite.com/essclub.

---

## Deploy to GitHub Pages (5 steps)

1. **Create a new GitHub repo** (e.g. `ess-website` or `essclub.github.io`)
2. **Upload all these files** to the repo (drag & drop or `git push`)
3. **Edit `_config.yml`** — set your `url` and `baseurl`
4. **In repo Settings → Pages** → set Source to **GitHub Actions**
5. **Push** — the site builds automatically via `.github/workflows/deploy.yml`

Your site will be live at `https://YOUR-USERNAME.github.io` (or your custom domain).

---

## Run Locally

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# → open http://localhost:4000
```

---

## File Structure

```
ess-jekyll/
├── _config.yml              ← site settings (UPDATE url/baseurl here)
├── Gemfile
├── .github/workflows/
│   └── deploy.yml           ← auto-deploys to GitHub Pages on push
│
├── _layouts/
│   ├── default.html         ← nav + footer wrapper for all pages
│   └── post.html            ← individual blog post layout
│
├── _sass/
│   └── ess.scss             ← ALL styles (one file, edit this)
│
├── assets/
│   ├── css/main.scss        ← entry point (imports _sass/ess.scss)
│   └── images/
│       └── logo.png         ← ADD YOUR LOGO HERE
│
├── _posts/                  ← blog posts (markdown files)
│   ├── 2026-04-05-year-end-celebration.md
│   ├── 2026-04-04-new-executive-positions.md
│   └── 2026-04-03-membership-renewal.md
│
├── index.html               ← Home page
├── about.html               ← About / Executive Team
├── updates.html             ← Blog listing
├── opportunities.html       ← Opportunities listing (fully populated)
└── contact.html             ← Contact page
```

---

## Adding Your Logo

Download your logo from the Wix CDN URL below, save it as `assets/images/logo.png`:

```
https://static.wixstatic.com/media/0a6d27_fedb6dba54d1403f886c72192f29c883~mv2.png/v1/fill/w_500,h_500,al_c,q_85/logow_transparentback_copy_2__1_-removebg-preview.png
```

The logo appears in the nav bar on every page, and as a placeholder in the team cards on the About page (replace with real photos when available).

---

## Adding Team Photos

In `about.html`, replace the logo `<img>` tags inside each `.team-card__avatar` div with real photos:

```html
<img src="/assets/images/team/claire.jpg" alt="Claire Rose">
```

Save photos to `assets/images/team/`.

---

## Writing New Blog Posts

Create a file in `_posts/` named `YYYY-MM-DD-your-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: 2026-09-01
category: Events       # or: News
image: https://your-image-url.jpg
description: Short description for SEO and previews.
---

Your post content here in Markdown.

**Bold text**, *italic*, [links](https://example.com), and bullet lists all work.

- Item one
- Item two
```

---

## Customising the Design

All design tokens are CSS custom properties at the top of `_sass/ess.scss`:

```scss
:root {
  --bg:           #faf8f5;   /* page background */
  --accent:       #7b5c3a;   /* brown accent (buttons, links, tags) */
  --primary:      #1a1a2e;   /* dark navy (headings, nav) */
  --font-head:    'Playfair Display', Georgia, serif;
  --font-body:    'Source Serif 4', Georgia, serif;
  --font-ui:      'DM Sans', system-ui, sans-serif;
  /* ... */
}
```

Change these variables and the whole site updates instantly.

---

## Contact Form

The contact form in `contact.html` points to Formspree. To activate it:

1. Sign up free at [formspree.io](https://formspree.io)
2. Create a new form and copy the endpoint (looks like `https://formspree.io/f/abcd1234`)
3. Replace `YOUR_FORM_ID` in `contact.html` with that URL

Alternatively, delete the `<form>` block — the direct email link (`ess.club@uleth.ca`) on the left side of the contact page works without any backend.

---

## Adding the Constitution PDF

Place the PDF at `assets/constitution.pdf`. The download button on the About page will link to it automatically.
