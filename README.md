# Deep Work Timer — Deployment Guide
## Ship to every platform, mostly free

---

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | Complete app — all screens, timer, audio, streak tracking |
| `manifest.json` | Makes the PWA installable like a native app |
| `sw.js` | Service worker — full offline support |
| `icon-192.png` | App icon (YOU must add this) |
| `icon-512.png` | App icon large (YOU must add this) |

### Creating icons (free)
Go to **canva.com** → 512×512 design:
- Background: #0f0f0f (near black)
- A simple amber circle or hourglass shape in #d4a853
- Export as PNG → save as `icon-512.png`
- Resize to 192×192 → save as `icon-192.png`

Or use **realfavicongenerator.net** to generate all sizes.

---

## STEP 1 — Deploy online (required before any app store)

### Option A: Netlify (recommended, 100% free)
1. Go to **netlify.com** → sign up free
2. Drag and drop this entire folder onto the Netlify dashboard
3. Get a live HTTPS URL: `https://deepwork-xyz123.netlify.app`
4. Done — your app is live worldwide

### Option B: GitHub Pages (also free)
1. Create account at **github.com**
2. New repository → name `deepwork-timer` → Public
3. Upload all files
4. Settings → Pages → Source: main / root
5. URL: `https://yourusername.github.io/deepwork-timer`

**HTTPS is required** for PWA features (service worker, install prompt).
Both Netlify and GitHub Pages provide it automatically for free.

---

## STORE 1 — Microsoft Store (FREE)

Microsoft Store accepts PWAs for free using **PWABuilder**.

### Steps:
1. Deploy your app online first (Netlify/GitHub Pages)
2. Go to **pwabuilder.com**
3. Enter your live URL → click "Start"
4. PWABuilder scores your PWA and shows what's ready
5. Click **"Package for Stores"** → choose **Windows**
6. Download the `.msix` package
7. Go to **partner.microsoft.com** → sign in with a free Microsoft account
8. Register as a developer → **Individual account = FREE**
9. Create new app → upload the `.msix` → set price to **Free**
10. Submit for review (usually approved within 3–7 days)

**Cost: $0** — Microsoft charges nothing for individual developer accounts.

---

## STORE 2 — Google Play Store ($25 one-time, then free forever)

Google Play accepts PWAs packaged as Android apps via **Trusted Web Activity (TWA)**.
PWABuilder handles this automatically.

### Steps:
1. Deploy your app online (Netlify/GitHub Pages)
2. Go to **pwabuilder.com** → enter your URL
3. Click **"Package for Stores"** → choose **Android**
4. Download the `.aab` (Android App Bundle) file
5. Go to **play.google.com/console** → sign up
6. Pay the **one-time $25 registration fee** (this is unavoidable)
7. Create new app → Upload → Internal testing first (recommended)
8. Fill in store listing: title, description, screenshots, icon
9. Set price: **Free**
10. Submit for review (2–7 days typical)

**Cost: $25 once, then $0 forever.**
You can publish unlimited apps after that with no additional fees.

### Screenshots needed for Google Play:
- At least 2 phone screenshots (min 320px wide, max 3840px)
- Open your app in Chrome → DevTools → Mobile view → screenshot
- Required sizes: 16:9 or 9:16 ratio recommended

---

## STORE 3 — Apple App Store ($99/year, NO free option)

Apple requires a paid Developer Program membership to publish publicly.
There is no workaround for public distribution.

### If you want to proceed:
1. Enroll at **developer.apple.com** → $99/year
2. Use **PWABuilder** → iOS package option (generates a basic Swift wrapper)
3. Or wrap with **Capacitor** (`npm install @capacitor/core @capacitor/ios`)
4. Open in Xcode → Archive → Distribute to App Store Connect
5. Set price: **Free**

### Free alternative for iPhone users:
iPhone users can still install your PWA without the App Store:
- Open URL in **Safari** → Share → **"Add to Home Screen"**
- Works offline, looks like a native app, no App Store needed
- This is the recommended path if you don't want to pay $99/year

---

## PWA Installation (works on all platforms, always free)

| Device | Instructions |
|--------|-------------|
| iPhone / iPad | Safari → Share icon → "Add to Home Screen" |
| Android | Chrome → 3-dot menu → "Add to Home Screen" (or auto-prompt) |
| Windows | Chrome/Edge → install icon in address bar |
| Mac | Chrome → install icon in address bar |
| Linux | Chrome → install icon in address bar |

---

## Privacy Policy (needed for Google Play & Microsoft Store)

Deep Work Timer collects zero user data.
Host this text on a free **Notion** page or **GitHub Pages**:

```
Deep Work Timer does not collect, store, or transmit any personal data.
All usage data (sessions, streaks) is stored locally on your device only
and never leaves it. No accounts. No analytics. No third-party services.
```

---

## Full cost summary

| Platform | Cost |
|----------|------|
| PWA (web) | $0 |
| Microsoft Store | $0 |
| Google Play | $25 once |
| Apple App Store | $99/year |
| Hosting (Netlify/GitHub) | $0 |

**Recommended launch order:**
1. Deploy as PWA on Netlify (free, instant)
2. Submit to Microsoft Store via PWABuilder (free)
3. Submit to Google Play ($25)
4. Apple only if budget allows ($99/year)
