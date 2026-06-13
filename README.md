# Camp Log

A pocket logbook for camping trips. Runs fully offline on your iPhone once installed, and all data stays on your device.

A poster-collage interface: giant Archivo wordmarks, color-blocked fields, woodgrain
waves, scattered ink marks and a die-cut starburst "seal" button. Four tabs along the
bottom (triangle / square / circle / diamond).

## What's inside

- **Log** (triangle) — your trips. The soonest upcoming trip headlines as a **Next Out**
  card with a countdown; everything else is listed below under **Trips**. Tap the **NEW LOG**
  seal to add one, tap a trip to edit, or swipe a row left for **Edit / Delete**.
- **Packing** (square) — a reusable gear manifest with a packed count. Tap an item to cross
  it off, swipe to edit/delete, **ADD ITEM** to add. "Reset all" clears the checkmarks
  before the next trip.
- **To-do** (circle) — tasks grouped under headings (e.g. *Before You Go*, *At Camp*). Tap to
  check, swipe to edit/delete, **ADD TASK** to add (with a group). "Clear done" sweeps
  finished tasks.
- **Campfire** (diamond) — placeholder for now ("coming soon").
- **Backup** — Export/Import links at the bottom of the Log tab save and restore everything as
  a JSON file. Do this occasionally; data lives only in your phone's browser storage.

On first launch the app is seeded with sample trips, a packing list and a few tasks so it
looks like the poster out of the box — edit or delete them freely.

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
