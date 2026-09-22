# Mithun KV — Portfolio

A single-page portfolio site: static HTML/CSS/JS, no build step, no dependencies.

## Structure
```
.
├── index.html          # the whole site
├── assets/
│   ├── photo.jpg        # profile photo
│   └── resume.pdf       # resume (view + download)
└── vercel.json
```

## Deploy to Vercel

**Option A — Vercel dashboard**
1. Push this folder to a GitHub repo.
2. Go to https://vercel.com/new, import the repo.
3. Framework preset: "Other" (no build command needed, output directory is `.`).
4. Deploy.

**Option B — Vercel CLI**
```bash
npm i -g vercel
cd this-folder
vercel        # first deploy, follow prompts
vercel --prod # promote to production
```

No environment variables, no build command, no server — it's a static site.

## Local preview
Just open `index.html` in a browser, or serve it locally:
```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Updating content
All project/skill/journey data lives in a set of JS arrays near the top of the
`<script>` block in `index.html` (`projects`, `skillDomains`, `journeyStages`,
etc.) — edit those objects rather than the rendered HTML, since the page
builds its sections from that data.

To swap the photo or resume, replace the files in `assets/` and keep the same
filenames (`photo.jpg`, `resume.pdf`), or update the paths in `index.html`.
