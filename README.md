# Listening Ledger

An installable web app that turns your YouTube Music history into deep listening stats: plays, replays, minutes, artists, monthly and yearly recaps, listening habits, sessions and repeat streaks.

Everything runs in your browser. Your history file is never uploaded anywhere; it's saved only on the device you import it on.

## Install it on your phone

**iPhone (Safari):** open the site, tap **Share**, then **Add to Home Screen**. It gets the Listening Ledger icon and opens full screen.

**Android (Chrome):** open the site, tap the **⋮** menu, then **Install app** (or **Add to Home screen**).

## Get your YouTube Music history

1. Go to [takeout.google.com](https://takeout.google.com) with the Google account you use for YouTube Music.
2. Click **Deselect all**, then tick **YouTube and YouTube Music**.
3. Click **All YouTube data included**, deselect all, tick only **history**.
4. Optional: under **Multiple formats**, set history to **JSON**.
5. Click **Next step** → **Create export**. Tip: choose **Export every 2 months for 1 year** to get fresh exports automatically.
6. Download the .zip from Google's email and import it in the app.

## Host it yourself on GitHub Pages

1. Create a repository (for example `listening-ledger`) and upload every file in this folder, keeping the `icons` folder.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, and click **Save**.
4. After a minute your app is live at `https://<your-username>.github.io/listening-ledger/`.

## Updating the app

After changing `index.html`, bump `VERSION` in `sw.js` (for example `ledger-v2`) so installed copies pick up the change.

## How the numbers work

Takeout records when each song started, not how long it played. Minutes are estimated from the gap until the next song, capped at that song's typical length, so skipped songs only count the seconds you heard. A song followed by another within 30 seconds counts as a quick skip. Plays made while YouTube history was paused aren't in the export.
