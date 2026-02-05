# ICE-STONE-CODE-PREVIEW (Site)

This is a lightweight static demo (Galaxy Code) containing `index.html` and `preview.html`.

Vercel deploy notes
- The project is a static site — no build step required.
- A `vercel.json` file is included with a rewrite so `/preview` maps to `/preview.html`.

Quick deploy (via Vercel CLI)
1. Install Vercel CLI:

```bash
npm i -g vercel
```

2. Login and deploy from project root:

```bash
vercel login
vercel --prod   -


Or connect the GitHub repo to Vercel through the Vercel dashboard and deploy the `main` (or default) branch.

Notes
- The site is entirely client-side; any edits to `index.html` / `preview.html` will be served directly.
- `vercel.json` sets a simple rewrite for nicer URLs; update it if you need additional routes or headers.

If you want, I can also add a small `package.json` and a simple static build pipeline, or set up repo-level headers (cache-control, CSP) before deploying.

Manual test checklist
- Open `index.html` in a browser and verify:
	- Settings gear opens the modal, and theme toggles persist across reloads.
	- About section fetches GitHub profile and repo stats when the modal opens (may be cached up to 12 hours).
	- Modal traps keyboard focus and closes on `Escape`.
https://drive.google.com/file/d/1N0Y61LkdDgXz9rlE462oTRdNrkbiHm-R/view?usp=drivesdk
```
- Open `preview.html` and verify:
	- Settings modal opens and displays user + repo data after opening.
	- Theme switch updates `data-theme` attribute and persists to `localStorage`.
	- Running code updates preview iframe and downloads function works.
https://drive.google.com/file/d/1N0Y61LkdDgXz9rlE462oTRdNrkbiHm-R/view?usp=drivesdk
```
Vercel notes
- After deploying, visit `/preview` to land on the preview page (rewrite added in `vercel.json`).

