# Fat to Fit Journey

A phone-first tracker for gym sessions, cardio, weigh-ins and food. It runs entirely in the browser: no server, no account, works offline once opened.

## Put it on GitHub Pages

1. Create a new repository on GitHub (for example `fit-journey`). It can be public or private (private Pages needs a paid plan).
2. Upload everything in this folder to the root of the repository, keeping the folders (`data`, `icons`, `vendor`). On github.com: **Add file → Upload files**, drag the whole folder contents in, commit.
3. Go to **Settings → Pages**. Under "Build and deployment", pick **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Add it to your home screen

- **iPhone (Safari):** open the link, tap **Share → Add to Home Screen**.
- **Android (Chrome):** open the link, tap **⋮ → Add to Home screen** (or **Install app**).

Open it from the home-screen icon from then on. On iPhone the home-screen app keeps its own storage, separate from Safari, so log from the icon, not from a Safari tab.

## Your data

- Everything you log is stored on the phone (IndexedDB), including photos.
- On first open, the app imports `data/seed.json`: 27 workouts (10 Aug to 22 Oct 2026), 64 cardio sessions with machine photos, 35 Cult.fit scale readings, and one starter preset per split ("Chest + Tri v1" etc.). Starter presets are added once; edit or delete them freely. If you already opened an older version, the import updates only the imported records (ids starting with `wa-`) and keeps everything you logged yourself.
- **Back up regularly:** Setup → Export backup creates one `.json` file with all entries and photos. Save it to Files or Google Drive. Setup → Import backup restores it, for example on a new phone.
- If your repository is public, `data/seed.json` (your past workouts) is public too. Anything you log in the app afterwards never leaves your phone.

## Updating the app

Replace `index.html` (and anything else that changed), then bump `VERSION` in `sw.js` (e.g. `ftf-v7`) so phones fetch the new copy. Close and reopen the app twice to see it.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole app |
| `form-notes.js` | Form guide text (how it works, cues, mistakes, tips) and form videos |
| `guide-data.js` | Exercise directory from the Strength Floor Guide (exercises, muscles, drawings, machine photos) |
| `data/seed.json` | Past workouts extracted from the WhatsApp log |
| `sw.js` | Offline support |
| `manifest.webmanifest`, `icons/` | Home-screen name and icon |
| `vendor/chart.umd.min.js` | Chart.js 4.4.1 (MIT licence, see `vendor/CHARTJS-LICENSE.md`) |
