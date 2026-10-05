# newbroman.github.io

Root user site. Hosts the `.well-known/assetlinks.json` needed for
the Polski Trener TWA Android app to open without falling back to Chrome.

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
will be updated and existing installs will need to be uninstalled first.

Keystores and their password files must never be committed here;
`.gitignore` now blocks the usual filenames.


## Setup
1. Upload all files in this repo to a GitHub repo named exactly `newbroman.github.io`
2. Enable GitHub Pages on the `main` branch
3. Verify: https://newbroman.github.io/.well-known/assetlinks.json

## Getting your SHA-256 fingerprint
In Android Studio, open the Terminal tab and run:
```
keytool -list -v -keystore signing.keystore
```
Enter your keystore password when prompted.
Copy the SHA-256 line and paste it into `.well-known/assetlinks.json`
replacing PASTE_YOUR_SHA256_FINGERPRINT_HERE
