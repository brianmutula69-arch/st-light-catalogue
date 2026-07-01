# ST Light Kenya catalogue — setup guide

## 1. Files in this project

```
index.html            the whole site (one file, no build step)
data/products.json     shop info + product list (admin mode edits this)
images/                product photos (admin mode uploads here)
```

Upload **all three** to your GitHub repo, keeping this exact folder layout,
then turn on GitHub Pages (Settings → Pages → Deploy from branch → main →
/root). The site works immediately even without step 2 below — admin
changes will just stay local to whichever device made them, same as before.

## 2. Turning on real shared publishing (recommended)

This is what makes an admin's upload on one phone show up for every visitor,
on every device — not just their own.

1. On GitHub: **Settings → Developer settings → Personal access tokens →
   Fine-grained tokens → Generate new token.**
2. Set:
   - **Repository access:** "Only select repositories" → pick this repo only.
   - **Permissions:** Repository → **Contents: Read and write.** Nothing else.
   - Give it an expiry (e.g. 90 days) — you'll just generate a new one later.
3. Copy the token (starts with `github_pat_...`).
4. On the live site: triple-click the logo → enter the admin password →
   tap the gear icon ("Connect") in the admin bar → fill in:
   - GitHub username/org
   - Repository name
   - Branch (usually `main`)
   - Paste the token
5. Tap **Save & test connection**. Once it says "Connected", every Save in
   admin mode commits straight to your repo. GitHub Pages rebuilds the site
   automatically — changes go live for everyone in roughly 30–60 seconds.

**Only give this token to people you trust with edit access to the repo.**
Don't tick "Remember on this device" on a shared/public computer — anyone
using admin mode afterwards would be able to publish using your token.

## 3. Using admin mode day-to-day

- Triple-click the logo to log in / out.
- **Pencil icon** on a product photo → edit name, category, price, badge,
  description, and swap the photo — all in one place.
- **X icon** on a product photo → delete that product (asks to confirm).
- **"Add product" button** (bottom right, admin mode only) → add a brand
  new product with its own photo and description. Works the same on a
  phone (tapping the photo area opens your camera/gallery picker) as on a
  computer (which also supports drag-and-drop).
- The pill next to the gear icon shows whether you're connected and
  publishing live, or only saving to this device.

## 4. Changing the admin password

Open `index.html`, find this line near the bottom:

```js
const ADMIN_PASSWORD = "stlight2024";
```

Change it, save, and re-publish `index.html` (commit it to GitHub like
normal, or re-upload it).
