# Setup guide

This is a customized al-folio starter with your bio, research projects, and
placeholder CV/publications structure already in place. Here's how to get it
live.

## 1. Create the repo

1. Create a new GitHub repo named exactly `YOUR_GITHUB_USERNAME.github.io`
   (this exact name is what makes GitHub Pages serve it at the domain root).
2. Push this folder's contents to that repo (as the initial commit — no need
   to preserve git history from the al-folio template).

```bash
cd al-folio-site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_GITHUB_USERNAME.github.io.git
git push -u origin main
```

## 2. Turn on GitHub Pages

In the repo: **Settings → Pages → Build and deployment → Source → GitHub
Actions**. The included `.github/workflows/deploy.yml` will build and deploy
the site automatically on every push to `main`. First build takes a few
minutes; your site will be live at `https://YOUR_GITHUB_USERNAME.github.io`.

## 3. Fill in the placeholders

Search the repo for `YOUR_` to find every spot that needs your real info:

- `_config.yml` — name, GitHub username, site URL
- `_data/socials.yml` — email, GitHub/LinkedIn usernames, Google Scholar ID
- `_data/cv.yml` — name, education, experience dates, policy-impact details
- `_data/repositories.yml` — GitHub username (pulls your public repos)

Also:

- Replace `assets/img/prof_pic.jpg` with a real photo of yourself.
- Add your CV as `assets/pdf/cv.pdf` (referenced from `_pages/cv.md`).
- Add real entries to `_bibliography/papers.bib` once you have papers to
  list (there's a commented example in the file).
- The three files in `_projects/` are drafted from your actual research
  (efficient grid interventions, nodal capacity expansion, feeder demand
  disaggregation) — expand them with real detail/figures when ready.
- `_news/announcement_1.md` mentions your policy impact (SB 1006, AB 1408) —
  edit it with specifics.
- `_pages/blog.md` and `_pages/teaching.md` are turned off (`nav: false`) for
  now since there's no real content yet — the `_posts/` folder still has
  al-folio's own feature-demo posts (math, code blocks, etc.); delete those
  or write your own, then flip `nav: true` when ready.
- Consider adding a short "Consulting" section — either as its own page in
  `_pages/` or just a paragraph on the about page (a draft line is already
  there) if you want to keep that door open.

## 4. Preview locally (optional)

You'll need Ruby + Bundler + Node installed locally (not available in this
sandbox):

```bash
bundle install
npm ci
bundle exec jekyll serve
```

Then visit `http://localhost:4000/`.

## Reference

- Full theme docs: https://github.com/alshedivat/al-folio (see `docs/` in
  the original repo for `CUSTOMIZE.md`, feature flags, etc.)
- `AGENTS.md` in this repo explains the v1.x plugin architecture if you (or
  an AI assistant) want to make deeper changes later.
