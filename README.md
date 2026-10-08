# Polski: Numbers, Dates & Time

Polish number, date and clock trainers combined in one app. This is the version behind the Polski Trener Android app.

**Live app:** https://newbroman.github.io/Polska/polski.html

## Security note: signing key (October 2026)

Until 5 October 2026 this repository contained the keystore used to sign the
Polski Trener Android app (`Polski trener liczb.apk`), together with its
passwords. Both files have been removed from the repository and its history,
but the key should be treated as public.

The app is not on Google Play, so the key cannot be reset. It is still in use.

- Only install the Polski Trener APK from this repository.
- Do not install a Polski Trener APK, or an "update" to it, from anywhere else,
  even if it installs over the existing app without complaint.
- The genuine signing certificate has this SHA-256 fingerprint:
  `75:21:A4:0A:7B:10:43:7C:BA:23:5F:DA:EA:70:7A:2B:4E:C0:B9:6C:61:26:66:92:86:D7:53:E4:66:10:89:B1`

If the app is later re-signed with a new key, this note and `assetlinks.json`
(in the `newbroman.github.io` repo) will be updated and existing installs will
need to be uninstalled first.

Keystores and their password files must never be committed here;
`.gitignore` blocks the usual filenames.

## Features

- **Numbers:** hear a Polish number and answer by tapping buttons (4, 8 or 12 choices) or typing digits or Polish. Options for negatives, decimals and fractions, plus Shopping, Prices, Sentences and Ordinals modes. Slow replay, speech input, and skip.
- **Calendar:** month view with Polish day names, a "Today is…" panel read aloud, public holidays, traditions, historic dates, name days and moon phase. Day view, Find Day, and your own appointments (once, daily, weekly or monthly).
- **Clock:** analogue clock in casual (12-hour) or formal (24-hour) style, with optional seconds, phonetic spelling, quiz mode, current time and random times.
- **Hands-free mode** for practising without touching the screen.
- Campaign levels with automatic or manual difficulty, XP, daily goal, streak, progress screen and review of mistakes.
- Grammar guide for numbers, dates and the clock, and an audio set-up guide for Android, iPhone/iPad and desktop.
- Light, dark or automatic theme. Progress is saved in the browser (`localStorage`).

## Using it

- **In a browser:** open the live link above. Polish speech uses your device's built-in Polish voice; the in-app Audio Setup guide shows how to install one. Chrome is recommended on Android and desktop, Safari on iPhone/iPad.
- **As a phone app:** install it from the browser menu ("Add to Home screen"), or on Android sideload `Polski trener liczb.apk` from this repository (see the security note above).

## Project structure

| File | Purpose |
|---|---|
| `polski.html` | The whole app: markup, styles and script |
| `manifest.json` | PWA manifest (name "Polski Trener", shortcuts to Numbers, Calendar and Clock) |
| `sw.js` | Service worker |
| `Polski trener liczb.apk`, `.aab` | Android build (Trusted Web Activity, package `io.github.newbroman.twa`) |
| `.well-known/assetlinks.json`, `assetlinks.json`, `_config.yml` | Copies of the Digital Asset Links file. Android checks the copy served from the domain root, which lives in the `newbroman.github.io` repo |
| `index.html` | Placeholder page for the folder root |
| `icon-*.png`, `ic_launcher*.png`, `screenshot-*.png` | Icons and store-style screenshots |

## Development

There is no build step. Serve the folder locally and open the app:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/polski.html
```

The manifest uses absolute `/Polska/` paths, so install behaviour is only realistic on the live site.

## Related repos

- [Polish-number-trainer](https://github.com/newbroman/Polish-number-trainer), [too-obvious](https://github.com/newbroman/too-obvious) and [Polish-clock](https://github.com/newbroman/Polish-clock) are the standalone number, date and clock trainers.
- [newbroman.github.io](https://github.com/newbroman/newbroman.github.io) hosts the root `assetlinks.json` the Android app depends on.

Built by Martin Hollingham.
