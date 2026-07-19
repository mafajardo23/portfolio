# Portfolio — setup notes

## File structure

```
index.html                     — the whole one-page site (home / work / skills / about / resume)
style.css                      — all styling (blue ticking stripe + yellow/pink accents)
projects/project-template.html — case study page template
assets/                        — put images + your resume PDF here (create this folder)
```

## Filling in content

Search each file for `UPDATE:` — every one marks something to personalize
(bio copy, dates, tags, links, images). Nothing will break if you leave
placeholders in temporarily; they're just visibly bracketed so you don't
ship them by accident.

## Adding a real project page

1. Duplicate `projects/project-template.html` → e.g. `projects/maps-onboarding.html`.
2. Fill in that new file's `UPDATE:` spots with the real case study.
3. In `index.html`, find the matching `.project-card` in the Work section and
   change its `href` from `projects/project-template.html` to your new filename.
4. Duplicate the `.project-card` block for additional projects — same pattern.

## Images and resume

Create an `assets/` folder next to `index.html`. Drop in:
- `portrait.jpg` (or whatever you name it) → swap into the hero `.hero-portrait` div
- photos for the About section → swap into the `.photo-box` divs
- `maria-fajardo-resume.pdf` → already linked from the Resume section, just add the file

Every placeholder box has an HTML comment right above it telling you exactly
what tag to swap in.

## Deploying to GitHub Pages

1. Create a new repo (or use an existing one), e.g. `mariafajardo.github.io`
   for a root-level personal site, or any repo name if you're fine with a
   `/reponame/` URL path.
2. Push these files to the repo:
   ```
   git init
   git add .
   git commit -m "portfolio site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```
3. In the repo on GitHub: Settings → Pages → Source → Deploy from branch →
   pick `main` / `/root` → Save.
4. Your site goes live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`
   (or `https://YOUR-USERNAME.github.io/` if the repo is named
   `YOUR-USERNAME.github.io`).
5. Pages usually takes 1–2 minutes to publish after each push.

## Nav behavior

- Work / Skills / About / Resume are anchor links — clicking them smooth-scrolls
  within `index.html`, they don't load new pages.
- Clicking a project card is the one exception — it navigates to its own
  page under `projects/` so you have room for case study writeups and media,
  with the same nav bar at the top to get back.
