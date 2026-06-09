# Hoda Rezvanjoo — personal website

A small, fast, static website. No build step, no framework — just HTML and one CSS file.
Matches the approved design: navy `#1B3A5C`, orange accent `#E87722`, Crimson Pro headings, Plus Jakarta Sans body.

## Structure

```
.
├── index.html          Home
├── work/index.html     Work (6 case studies)
├── research/index.html Research notes
├── writing/index.html  Writing feed
├── about/index.html    About + CV/LinkedIn
├── contact/index.html  Contact form + direct links
├── assets/
│   ├── style.css       Shared header / footer / layout styles
│   └── logo.webp       Site logo / favicon
├── .nojekyll           Tells GitHub Pages to serve files as-is
└── README.md
```

## Put it on GitHub + GitHub Pages

1. Create a new repository (e.g. `hoda-site`).
2. Upload **everything inside this folder** to the repo root (drag the files into GitHub's "Add file → Upload files", or use git).
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait ~1 minute. Your site is live at `https://<username>.github.io/<repo>/`.

> The `.nojekyll` file is already included so Pages serves the folders correctly.

### Custom domain (optional)
If you want `hodarezvanjoo.com` to point here instead of WordPress: in **Settings → Pages → Custom domain**, enter the domain, then add the DNS records GitHub shows you at your domain registrar.

## Before you publish — two quick adds

1. **Your photo** — drop a portrait at `assets/portrait.jpg` (about 600×750px). The About page shows it automatically; until then it shows a labelled placeholder.
2. **Your CV** — drop your PDF at the repo root as `cv.pdf`. Every "Download CV" button links to it.

## Contact form

Out of the box the form uses `mailto:` — clicking **Send** opens the visitor's email app with the message pre-filled. To receive submissions straight to your inbox (no email-app step):

1. Sign up free at **formspree.io** and create a form for `hrezvanjoo@gmail.com`.
2. In `contact/index.html`, replace:
   ```html
   <form action="mailto:hrezvanjoo@gmail.com" method="post" enctype="text/plain" ...>
   ```
   with:
   ```html
   <form action="https://formspree.io/f/YOUR_ID" method="post" ...>
   ```

## Editing

- **Colours, header, footer, fonts, form fields** → `assets/style.css` (one place, applies to every page).
- **Page text and links** → edit the relevant `*/index.html`. Styles are inline and self-explanatory.
- All internal links are relative, so the site works at any path (project Pages, custom domain, or opened locally).

## Notes

- Fonts load from Google Fonts. The site needs an internet connection for the exact fonts; otherwise it falls back to Georgia (headings) and a system sans (body).
- The Work page links out to each project's GitHub repo and live Streamlit app. Individual case-study detail pages aren't included in this static build — add them as `work/<project-slug>/index.html` later if you want them.
