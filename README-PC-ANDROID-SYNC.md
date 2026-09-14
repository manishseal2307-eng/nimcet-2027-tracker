# NIMCET 2027 Tracker — PC + Android/iPhone

This package upgrades the original standalone tracker into a PWA-ready version.

## What changed
- Responsive UI remains usable on phone and PC.
- PWA manifest + service worker for install-to-home-screen/desktop and offline app-shell caching.
- Local-first storage is preserved.
- Optional automatic cloud sync using Firebase Authentication + Firestore.
- Same email/password account can be used on phone and PC.
- The tracker continues to work if cloud sync is not configured.

## Important
A browser cannot make a local HTML file into a fully installable/syncing PWA. Host this folder on HTTPS (GitHub Pages, Netlify, Cloudflare Pages, etc.).

## Enable cross-device sync
1. Create a Firebase project.
2. Add a Web app and copy its Firebase config into `firebase-config.js`.
3. In Firebase Authentication, enable **Email/Password** sign-in.
4. Create a Firestore database.
5. Apply the rules from `firebase.rules`.
6. Host the folder on HTTPS.
7. Open the app on PC, go to **Settings → Cross-device Sync**, create an account.
8. Open the same app URL on your phone and sign in with the same account.

## Install
- Android Chrome: open the hosted app → browser menu → **Install app** / **Add to Home screen**.
- iPhone Safari: open the hosted app → Share → **Add to Home Screen**.
- PC Chrome/Edge: open the hosted app → install icon in the address bar or browser menu.

## Notes
- Firebase client configuration is not a server secret; Firestore security rules protect each user's document.
- Do not put a Firebase Admin SDK/private key into `firebase-config.js`.
- NIMCET 2027 date in the tracker remains a tentative planning date until the official notification is released.
