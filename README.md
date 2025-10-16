# Static Invoice Links (GitHub Pages)

This is a static invoice generator + viewer that runs entirely on GitHub Pages (no server, no Stripe).

## How to deploy on GitHub Pages
1. Create (or go to) a GitHub repository. Name can be anything; to serve at `https://yourusername.github.io/` create a repo named `<yourusername>.github.io`. Otherwise you will get `https://yourusername.github.io/repo-name/`.
2. Add these files to the repo root:
   - `index.html`
   - `invoice.html`
   - `README.md`
3. Commit the files.
4. In your repo: **Settings → Pages** → Source: `main` branch, folder `/ (root)` → Save.
5. Wait a minute. Your site will be available at the Pages URL GitHub shows.

## How it works
- `index.html` builds a base64-encoded payload and produces a link:
  `https://.../invoice.html?d=<payload>`
- `invoice.html` decodes the payload and displays invoice fields (id, name, amount, notes).
- This is a static display only: it does **not** accept or detect payments.

## Notes & security
- The token is just encoded JSON (no signature). Anyone with the link can view or edit the query string.
- If you need tamper-proof signed links or payment confirmation, you need a small server (Vercel/Netlify) or a third-party payment provider.
