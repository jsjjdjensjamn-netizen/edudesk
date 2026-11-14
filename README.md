# EduDesk – Tuition Manager

Turn this web app into an Android APK using GitHub Actions.

## Folder structure

```
EduDesk/
├── index.html                 ← Main app
├── manifest.webmanifest       ← PWA manifest
├── sw.js                      ← Service worker (offline)
├── package.json
├── capacitor.config.json
├── icons/                     ← App icons (replace with real PNGs)
│   ├── icon-192.png
│   ├── icon-512.png
│   ├── apple-touch-icon.png
│   ├── favicon-32.png
│   └── favicon-16.png
└── .github/workflows/
    └── build-apk.yml          ← Auto builds APK on every push
```

## How to get the APK

### Option A – Automatic (Recommended)

1. Create a new GitHub repository
2. Upload this entire `EduDesk` folder to the repository
3. Go to the **Actions** tab on GitHub
4. Run the workflow **Build Android APK** (or just push any change)
5. After 2–4 minutes, download the APK from the **Artifacts** section

### Option B – Local build (if you have Android Studio)

```bash
npm install
npx cap add android
npx cap sync
npx cap open android
```

Then in Android Studio: **Build → Build Bundle(s) / APK(s) → Build APK(s)**

## Important: Icons

The icons folder currently has placeholder notes.  
You should replace them with real PNG icons:

- `icons/icon-192.png` (192×192)
- `icons/icon-512.png` (512×512)
- `icons/apple-touch-icon.png` (180×180)
- `icons/favicon-32.png` (32×32)
- `icons/favicon-16.png` (16×16)

You can generate them free from: https://www.pwabuilder.com/imageGenerator  
or any favicon generator.

## Notes

- The app works fully offline after the first load.
- Data is stored on the device (localStorage) + optional Firebase sync.
- Change `appId` in `capacitor.config.json` if you want a different package name.
