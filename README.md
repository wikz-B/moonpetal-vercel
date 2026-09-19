# Moonpetal — Vercel edition

Your original Moonpetal player, prepared for static hosting on Vercel.
The cat, flower, cover artwork, colors, playlists, and playback controls are retained.
No framework, npm dependencies, backend, API keys, or build step is required.

## Deploy through GitHub + Vercel

1. Extract the ZIP.
2. Create a GitHub repository and upload the CONTENTS of `moonpetal-vercel`.
   The repository root should contain `vercel.json`, `README.md`, and `public/`.
3. In Vercel, choose Add New > Project and import that repository.
4. Use these settings if prompted:
   - Framework Preset: Other
   - Root Directory: the folder containing vercel.json (repository root if uploaded as above)
   - Build Command: empty (enable Override if needed)
   - Output Directory: public
   - Install Command: empty
   - Environment Variables: none
5. Click Deploy, then open the production URL.

The included vercel.json supplies the static output and empty build/install commands.
Vercel configuration reference: https://vercel.com/docs/project-configuration

## Alternative: Vercel CLI

With Node.js installed, open a terminal inside moonpetal-vercel and run:

```sh
npx vercel --prod
```

Sign in when prompted and follow the project setup prompts. Use the settings above.

## Preview locally

With Python installed, run from moonpetal-vercel:

```sh
python -m http.server 8000 --directory public
```

Visit http://localhost:8000. Use a local server rather than double-clicking index.html.

## Edit the project

- public/index.html: layout and inline SVG artwork
- public/styles.css: appearance and responsive layouts
- public/app.js: playback, playlists, search, artwork, and local database
- vercel.json: hosting settings

## Music and storage

Click Add music or drop audio files onto the page. Select a song to play it.
Create playlists using New playlist; use + beside songs to add them.
Click the current cover to choose custom artwork. Space toggles playback.
Shuffle, repeat, seek, volume, mute, compact mode, and playlist ordering are retained.

Music and artwork are stored only in the visitor's browser using IndexedDB.
There is no shared streaming catalog, cloud backup, or account synchronization.
Music previously imported into the offline HTML will NOT automatically appear
on the hosted website. Import those original audio files again.
Keep using the same production domain, browser, and profile. Preview URLs,
a different custom domain, and other devices have separate collections.
Clearing browser data or browser storage eviction can remove saved collections;
keep your original audio files as backups. Storage limits vary by browser/device.

Internet is required to load or reopen the website. Once loaded, local audio
playback does not need internet. This version does not install an offline cache.
MP3 and WAV are recommended; other formats depend on browser support.
Song titles come from filenames; embedded tags are not read. Animated bars
are decorative. No audio files are bundled with the source.

## Validation

JavaScript syntax, HTML element references, local asset paths, configuration JSON,
and HTTP serving for the page, CSS, and JavaScript were checked successfully.
Browser playback and visual checks could not run because a browser executable
was unavailable in the preparation environment. After deployment, import a song,
play/pause it, create a playlist, and reload to check saved data on your device.
