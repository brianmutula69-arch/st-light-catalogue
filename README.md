# images/

Product photos live here, one file per product, named after the product's `id`
(e.g. `sol-001.jpg`). You normally never touch this folder by hand — Admin
Mode on the site uploads here automatically once it's connected to GitHub
(gear icon in the admin bar).

If you ever add a photo manually:
1. Name the file exactly `{product-id}.jpg` (or `.png`/`.webp`) — match the
   `id` field for that product in `data/products.json`.
2. Set that product's `"img"` field in `data/products.json` to
   `"images/{product-id}.jpg"`.
