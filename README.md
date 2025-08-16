# MedStudy Hub

A lightweight, GitHub Pages–ready study website with four topics: **Pedia**, **OBGYN**, **Surgery**, **Medicine**.  
This starter enables **OBGYN** with a searchable list and a quiz mode. Add the other topics later by dropping JSON files in `data/`.

## Quick Start (GitHub Pages)

1. Create a new GitHub repo (e.g., `medstudy-hub`).
2. Upload **all** files from this folder to the repo root (`index.html`, `styles.css`, `app.js`, `assets/`, `data/`).
3. Commit to the `main` branch.
4. In the repo: **Settings → Pages**  
   - *Build and deployment*: **Deploy from a branch**  
   - *Branch*: `main` and `/ (root)` → **Save**  
5. Wait ~30–60 seconds until GitHub builds your site. Your URL will be:
   `https://<your-username>.github.io/<your-repo>/`

> Alternative: use **GitHub Desktop** or **git** CLI (see below).

## Add more topics

- Copy `data/obgyn.json` to a new file like `data/pedia.json`. Follow the same schema
  (`id`, `question`, `options`, `answer`, `explanation?`, `source?`).
- In `app.js`, add a new route/render function for the topic or reuse the OBGYN renderer and change the file it loads.

## Local preview

Just open `index.html` directly in your browser. (If your browser blocks `fetch` for local files, run a tiny server:  
Python: `python3 -m http.server 8080` and visit http://localhost:8080)

## CLI deploy (optional)

```bash
# in an empty folder
git init
git remote add origin https://github.com/<you>/medstudy-hub.git
git checkout -b main
cp -R * path/to/this/project/* .
git add .
git commit -m "Initial site"
git push -u origin main
```

Then enable Pages as above (Settings → Pages → Deploy from a branch).

## Notes

- This SPA uses a hash router (`#/`) so it works great on GitHub Pages without extra configuration.
- Design is custom CSS (no frameworks) to keep it simple and fast.
- Dark / light mode toggle is built-in.
- The OBGYN items included here were adapted from your provided document for bootstrapping the content.
