# Manual SRE™ — Artisanal Infrastructure Care

A satirical parody of enterprise SaaS landing pages, mocking the inefficiencies of manual SRE practices.

## Stack

- Single `index.html` file — no build step required
- Tailwind CSS via CDN
- Google Fonts: Space Grotesk + Space Mono
- Vanilla JavaScript only

## Replacing Placeholder Assets

Two placeholder animation zones exist in the HTML:

1. **Hero section** — `🎩🔧` placeholder labeled `// replace with chaplin.gif`
   - Drop a `chaplin.gif` (or any `.gif`/`.webp`) into this folder
   - Replace the `.chaplin-box` div contents with `<img src="chaplin.gif" alt="Charlie Chaplin" />`

2. **Cloud Spending section** — money fire placeholder labeled `// replace with money-fire.gif`
   - Same pattern: drop the file in, swap the `.money-box` contents

---

## Deployment

### Netlify

**Option A — Drag & Drop (fastest)**

1. Go to [app.netlify.com](https://app.netlify.com) and sign in
2. Click **"Add new site"** → **"Deploy manually"**
3. Drag the entire `manual-sre-site/` folder onto the drop zone
4. Netlify assigns a random subdomain instantly (e.g. `happy-turing-abc123.netlify.app`)
5. Optionally configure a custom domain under **Site settings → Domain management**

**Option B — GitHub Connect**

1. Push this folder to a GitHub repository
2. In Netlify: **"Add new site"** → **"Import an existing project"** → connect GitHub
3. Select the repository
4. Build settings:
   - **Build command:** _(leave blank)_
   - **Publish directory:** `.` (or the folder name if the repo root is the parent)
5. Click **Deploy site** — Netlify auto-deploys on every push to `main`

---

### Vercel

**Option A — Drag & Drop**

1. Go to [vercel.com/new](https://vercel.com/new) and sign in
2. Click **"Continue with..."** then look for the **Deploy** tab
3. Use the Vercel CLI for the fastest drag-equivalent:
   ```bash
   npm i -g vercel
   cd /Users/ilanadler/manual-sre-site
   vercel
   ```
4. Follow the prompts — no framework preset needed, output directory is `.`

**Option B — GitHub Connect**

1. Push this folder to a GitHub repository
2. In Vercel: **"Add New Project"** → import the repository
3. Framework preset: **Other**
4. Root directory: `.` (or the subfolder if nested)
5. Build & output settings: leave everything blank (static file, no build step)
6. Click **Deploy** — Vercel auto-deploys on every push to `main`

---

## Local Preview

No server needed for basic viewing — open the file directly:

```bash
open /Users/ilanadler/manual-sre-site/index.html
```

For a proper local server (recommended, avoids CORS quirks with fonts):

```bash
# Python 3
cd /Users/ilanadler/manual-sre-site && python3 -m http.server 8080

# Node (npx)
npx serve /Users/ilanadler/manual-sre-site
```

Then visit `http://localhost:8080`.
