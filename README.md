# piankeapp.github.io

Public site for **片刻 / Pianke** (fully-offline business-card scanner), served by GitHub Pages under
the neutral `piankeapp` organization: the bilingual landing page, the app's privacy policies, the
support page, the `/get` store redirect used by flyers and in-app shares, and a few guide articles.

- `index.html` — bilingual landing page (zh-TW default, EN toggle via `data-en` / `data-en-html`;
  images and labels swap with `data-en-src` / `data-en-alt` / `data-en-aria`). Theme follows the OS
  unless the visitor toggles it (the choice is kept in `localStorage`).
- `privacy-policy.html` / `privacy-policy-ios.html` — the privacy policies (bilingual). These are the
  URLs pasted into Play Console and App Store Connect.
- `get.html` — `/get?<tag>` sends phones to the right store and tags the Play install referrer.

### Images (`img/`)

Everything the page shows is self-hosted here — no third-party CSS, JS, fonts or trackers.

- `shot-*.webp` — app screenshots, 600×1200 WebP (q80), made from the 1200×2400 Play store
  screenshots in the app repo's `design/store-screenshots/` (synthetic demo data only, no real
  people's cards). Regenerate after a re-capture:
  ```
  python -c "from PIL import Image; import sys; [Image.open(f).convert('RGB').resize((600,1200), Image.LANCZOS).save('img/shot-'+f.rsplit('/',1)[-1][:-4]+'.webp', 'WEBP', quality=80, method=6) for f in sys.argv[1:]]" <path>/design/store-screenshots/0*.png
  ```
- `badge-google-play-{zh,en}.png` — official Google Play badges (play.google.com/intl/en_us/badges),
  transparent padding trimmed, scaled to 144 px tall, palette-quantized. Do not recolor or redraw.
- `badge-app-store-{zh,en}.svg` — official black "Download on the App Store" badges from Apple
  Marketing Tools (toolbox.marketingtools.apple.com), unmodified.
- `qr-get.svg` — QR for `https://piankeapp.github.io/get?site` (the `site` tag counts home-page scans apart from flyers)
  (`python -c "import qrcode, qrcode.image.svg as s; qrcode.make('https://piankeapp.github.io/get?site', image_factory=s.SvgPathFillImage, border=2).save('img/qr-get.svg')"`).

Badges render 48 px tall (44 px on phones); keep at least ¼ of the badge height as clear space.

### What's new (`index.html#new`) — update on every release

- Newest feature goes in the `.spot` spotlight (and the hero `NEW` pill); the previous spotlight
  moves to the top of the `.log` list.
- Tag every item with the **first** Android / iOS version that supports it.
  `.vtag.live` = that version is downloadable in the store now; `.vtag.soon` = built but not released.
- Never mark a version `.live` before it is actually in the store. When a `.soon` version ships,
  flip it to `.live` and change the text to 已上架 / available.

### Pricing (`index.html#pricing`)

- When the store price changes (incl. any founding/launch discount), update the `#pricing` section
  (plan cards and the comparison table) and the price in the `.proof` stat row under the hero in the
  same change.
- Only verifiable facts in the stat row and comparison — no download/user counts or ratings, never
  name a competitor or quote its price.

> This repo is intentionally **separate** from the app source so nothing private (source, internal
> business strategy, the dashboard) is ever published. Only these public pages live here.

Published URL (root-site repo → Pages auto-enabled): `https://piankeapp.github.io/privacy-policy.html`
