# Tabby — Landing Page

Single-page marketing site for Tabby, the macOS menu bar bookmark app.

## Deploy to Vercel

### Option 1 — Drag and drop (fastest)

1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag this entire folder onto the page
3. Click Deploy
4. Done — you'll get a URL like `tabby-xyz.vercel.app`

### Option 2 — Vercel CLI

```bash
npm install -g vercel
cd tabby-deploy
vercel
```

Follow the prompts. First deploy creates the project; subsequent `vercel --prod` deploys ship to production.

### Option 3 — GitHub integration

1. Push this folder to a GitHub repo
2. Import the repo in Vercel
3. Every push to `main` auto-deploys

## Custom domain

Once deployed, add your domain in Vercel → Project → Settings → Domains. Point your DNS A record to `76.76.21.21` or CNAME to `cname.vercel-dns.com`.

## Project structure

```
tabby-deploy/
├── index.html           ← the page itself
├── vercel.json          ← config: clean URLs, force download on DMG
├── downloads/
│   └── Tabby-1.0.dmg    ← drop your DMG here
└── screenshots/
    └── menubar.png      ← drop your screenshots here
```

## Before going live

1. **Add the DMG** — drop `Tabby-1.0.dmg` into `/downloads/`
2. **Add a screenshot** — drop `menubar.png` into `/screenshots/` and update `index.html` (see `screenshots/README.txt`)
3. **Update links** — search `index.html` for `yourname` and `yourhandle` and replace with your GitHub and Twitter usernames
4. **Update the email** — replace `hello@tabby.app` with your real address
5. **Check file size** — update the `v1.0 · 4.2 MB` text to match your actual DMG size

## Updating the page

For a new release:

1. Build the new DMG and drop it in `/downloads/` (e.g. `Tabby-1.1.dmg`)
2. In `index.html`, update the `href` on the download button and the version label below it
3. Redeploy (`vercel --prod` or push to GitHub)

That's the whole workflow.
