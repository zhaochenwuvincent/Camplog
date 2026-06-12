# Camp Log

A pocket logbook for camping trips. Runs fully offline on your iPhone once installed, and all data stays on your device.

## What's inside

- **Trips** — a trail-style timeline. Upcoming trips sit above the "YOU ARE HERE" marker, past trips below it. Tap any trip to edit or delete it. Tap a tag chip to filter.
- **Checklist** — a reusable packing list (seeded with basics; edit freely). "Uncheck all" resets it before the next trip.
- **To-do** — a simple task list with "Clear done".
- **Backup** — Export/Import buttons at the bottom of the Trips tab save and restore everything as a JSON file. Do this occasionally; data lives only in your phone's browser storage.

## Deploy with GitHub Pages (one time, ~5 minutes)

1. Sign in at github.com and create a **new public repository**, e.g. `camplog`.
2. Upload everything in this folder (keep the `icons/` folder structure): `index.html`, `sw.js`, `manifest.json`, `icons/`.
3. In the repo: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**.
4. Wait a minute, then open `https://YOURNAME.github.io/camplog/` in **Safari** on your iPhone.

Any free static host works the same way (Netlify, Cloudflare Pages, etc.).

## Install on iPhone

1. Open the URL in Safari.
2. Tap the **Share** button → **Add to Home Screen** → **Add**.
3. Open it from the new home-screen icon once **while online** so the service worker can cache everything.

After that first launch it works with no connection at all — airplane mode, no signal at a campsite, anything.

## Updating the app later

Edit the files in the repo, then open `sw.js` and bump the version string (`camplog-v1` → `camplog-v2`). That tells installed copies to fetch the new files on their next online launch.

## Notes

- Data is stored in `localStorage` under the key `camplog.v1`. Installed home-screen apps on iOS keep their storage separate from Safari and it isn't subject to Safari's cleanup — but deleting the app icon deletes the data, so export a backup before removing or reinstalling.
- Dark mode follows your phone's system setting (lantern-friendly at night).
