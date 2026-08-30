# FastFit — 16:8 Plan Tracker (PWA)

A single-page web app that tracks your intermittent-fasting window, meals,
supplements, workouts and weigh-ins. Once hosted on GitHub Pages it installs
to your phone like a normal app and works offline.

## Files
- `index.html` — the app
- `manifest.json` — app name, icons, standalone display
- `sw.js` — service worker (offline cache)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `favicon-32.png`

---

## Put it online with GitHub Pages (no coding, all in the browser)

1. Sign in to GitHub as **mechkutlu1**.
2. Click **New repository**. Name it **`fastfit`**, set it **Public**, and create it.
3. On the new repo page choose **uploading an existing file**.
4. Drag in **all the files** from this folder (index.html, manifest.json, sw.js and every icon). Click **Commit changes**.
5. Go to **Settings -> Pages**.
6. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick branch **`main`** and folder **`/ (root)`**, then **Save**.
7. Wait about a minute. Your app is live at:

   **https://mechkutlu1.github.io/fastfit/**

Open that link on your phone.

## Install on your phone
- **Android / Chrome:** open the link, then use the **Add to home screen** button on the app's Setup tab (or the browser menu).
- **iPhone / Safari:** open the link, tap the **Share** icon, then **Add to Home Screen**.

The app now opens full-screen from your home screen and runs offline.

---

## Alternative: command line (git)

```bash
git clone https://github.com/mechkutlu1/fastfit.git
cd fastfit
# copy all files from this folder into here
git add .
git commit -m "FastFit PWA"
git push origin main
```

Then enable Pages as in steps 5–7 above.

---

## Notes on reminders
- In-app reminders and notifications fire while the app is open (enable them on the Fasting tab).
- For alarms that ring when the app is closed, use the **Download calendar file** button on the Setup tab and open the `.ics` in your phone's calendar. This is the reliable background alarm layer.
- All your data (weigh-ins, ticks, settings) stays on your device in the browser. Nothing is uploaded anywhere.

## Updating the app later
Re-upload a changed file to the repo. The service worker cache version is set in `sw.js` (`const CACHE = 'fastfit-v1'`). If you change the app and it looks stale on a device, bump that to `fastfit-v2` so phones fetch the new version.
