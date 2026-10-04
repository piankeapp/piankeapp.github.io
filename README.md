# piankeapp.github.io

Public site for **片刻 / Pianke** (fully-offline business-card scanner) — hosts the app's
**privacy policy** for Google Play via GitHub Pages, under the neutral `piankeapp` organization.

- `privacy-policy.html` — the privacy policy (bilingual zh-TW / en). This is the URL to paste into
  Play Console → App content → Privacy policy.
- `index.html` — bilingual landing page (zh-TW default, EN toggle via `data-en` attributes).

### What's new (`index.html#new`) — update on every release

- Newest feature goes in the `.spot` spotlight (and the hero `NEW` pill); the previous spotlight
  moves to the top of the `.log` list.
- Tag every item with the **first** Android / iOS version that supports it.
  `.vtag.live` = that version is downloadable in the store now; `.vtag.soon` = built but not released.
- Never mark a version `.live` before it is actually in the store. When a `.soon` version ships,
  flip it to `.live` and change the text to 已上架 / available.

> This repo is intentionally **separate** from the app source so nothing private (source, internal
> business strategy, the dashboard) is ever published. Only these public pages live here.

Published URL (root-site repo → Pages auto-enabled): `https://piankeapp.github.io/privacy-policy.html`
