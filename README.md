# IROS 2026 blog (GitHub Pages)

Static site: essay (`index.html`), full album (`gallery.html`), `styles.css`, and web-sized JPEGs.

**Upload this `blog/` folder only.** Leave the 1.4 GB camera originals in `../Photos/`.

## GitHub limits (this is the distinction)

You are right that **individual file size** is the hard block, not “GitHub cannot hold 1.4 GB.”

| Limit | What it means for these photos |
|---|---|
| **100 MB per file** (hard) | Your originals are ~5–10 MB. Git will accept every frame. |
| **50 MB per file** | Warning only. You will not see it. |
| **Repo size** | Recommended under **1 GB**; GitHub asks you to stay under **5 GB**. 1.4 GB of originals in a *normal* repo would probably push, but it is slower to clone and against the “keep it small” advice. |
| **GitHub Pages published site** | **Must be ≤ 1 GB.** [Docs](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits). 1.4 GB of originals would **fail Pages** even if Git stored the files. |

So: originals *can* live in a GitHub **archive repo** (private, not Pages). They should **not** be the Pages site.

This blog is ~35 MB (hero images + all 222 frames at ~1400 px). That is well inside Pages.

## What to put where

| Content | Place |
|---|---|
| This `blog/` folder (~35 MB) | **GitHub Pages** — `https://YOURUSER.github.io/iros-2026-pittsburgh/` |
| 6000×4000 originals (1.4 GB) | Keep on **OneDrive** (already there). Optional: a **private GitHub repo** that is *not* a Pages site, if you want a git backup. |
| “See every photo” on the web | Already on `gallery.html` using the compressed copies |

Do not copy `../Photos/` into this folder.

## Publish

```bash
cd blog
git init
git add index.html gallery.html album.json styles.css images README.md
git commit -m "IROS 2026 Pittsburgh photo essay"
git branch -M main
git remote add origin git@github.com:YOURUSER/iros-2026-pittsburgh.git
git push -u origin main
```

GitHub → **Settings → Pages → Deploy from a branch → `main` / root**.

Preview locally: `python3 -m http.server 8000` then open http://127.0.0.1:8000
