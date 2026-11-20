# Creator Type Quiz

A shareable creator-personality quiz by **@icyspicee_**. Visitors answer 8 questions and get a
story-sized card (with mascot, superpower, blind spot, brand-fit and a copyable caption) they can
download. There are two separate interfaces that share nothing visible to the public:

- **Public quiz** — `/` — what you share with your audience. No admin UI anywhere.
- **Admin editor** — `/admin` (or `/#admin`) — edit the questions. Passcode-gated.

## Files

```
index.html        the whole app (quiz + admin), self-contained apart from the mascots
assets/*.png      the 8 creator-type mascots
vercel.json       serves the admin editor at /admin on Vercel
netlify.toml      same, for Netlify
```

## Deploy from GitHub

1. Create a new repository and push these files to it (keep the folder structure):
   ```bash
   git init
   git add .
   git commit -m "Creator Type Quiz"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
2. Pick a host:
   - **Vercel** — "Add New → Project", import the repo, Framework preset **Other**, deploy.
     `/admin` works via `vercel.json`.
   - **Netlify** — "Add new site → Import from Git", pick the repo, deploy.
     `/admin` works via `netlify.toml`.
   - **GitHub Pages** — Settings → Pages → deploy from `main` / root.
     Pages has no rewrites, so use **`/#admin`** for the editor (the plain `/admin` path won't work there).

## Admin

- Open `/admin` (or `/#admin`), enter the passcode, and edit questions, answers, scoring, add/remove questions.
- Default passcode is `icyspicee` — change it in `index.html` (search for `ADMIN_CODE`).
- On a static host, admin edits save to **your browser** as a live preview. To publish new questions
  to every visitor, use **Copy as JSON** in the editor and redeploy, or tell whoever maintains the repo.

## Notes

- The downloaded card is a 1080×1920 PNG, ready for stories.
- To swap a mascot, replace the matching file in `assets/` (keep the filename) and redeploy.
