# 🚀 SwiftNeo Official Website

![SwiftNeo Logo](https://via.placeholder.com/400x200/0a0a16/00f3ff?text=SwiftNeo)
![License](https://img.shields.io/badge/License-Proprietary-red.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)
![Android](https://img.shields.io/badge/Android-6.0%2B-blue.svg)

**Premium YouTube Experience. Zero Cost. Zero Ads.**

SwiftNeo is a free, ad-free YouTube client for Android with premium features like background playback, video downloads, floating mini-player, and 100% ad blocking.

⚠️ **IMPORTANT**: SwiftNeo is **FREE** to use but **CLOSED-SOURCE** (proprietary). Binary distribution only via official channels.

---

## 📱 Features

- 🛡️ **100% Ad Blocker** - Zero pre-roll, mid-roll, or banner ads
- 📱 **Floating Mini-Player** - Resizable PiP window for multitasking
- 🎧 **Background Audio** - Listen with screen off or in background
- ⬇️ **Smart Download Manager** - Pause, resume, cancel downloads
- 🌐 **Direct Share** - Share from YouTube WebView to SwiftNeo
- 📜 **Smart History** - 3-dot menu, multi-select, clear all
- 🎯 **Zero Data Collection** - No telemetry, no analytics, no tracking
- 🔒 **Privacy-Focused** - All data stored locally on your device

---

## 🌐 Website

Visit the official website: **https://`<your-username>`.github.io/SwiftNeo-Website/**

The website includes:
- Bilingual support (English/Hindi)
- APK download with SHA-256 verification
- VirusTotal security scan report
- Complete installation guide
- Security & privacy transparency

---

## 📂 Repository Structure

```
SwiftNeo-Website/
├── index.html                 # Main website (single file, all CSS/JS embedded)
├── assets/
│   ├── screenshots/          # App screenshots (webp format)
│   │   ├── hero.webp
│   │   ├── player.webp
│   │   ├── pip.webp
│   │   ├── downloads.webp
│   │   └── history.webp
│   └── icons/
│       ├── favicon.ico       # 32x32 neon "S" icon
│       └── logo.svg          # Vector SwiftNeo logo
├── SECURITY.txt              # Security policy + VirusTotal scan link
├── PRIVACY.txt               # Privacy policy (zero data collection)
├── LICENSE.txt               # EULA for end-users
└── README.md                 # This file
```

---

## 🚀 Deployment Instructions

### Step 1: Create GitHub Repository

1. Go to GitHub and create a new repository
2. Name it: `SwiftNeo-Website`
3. Make it **Public**
4. Click "Create repository"

### Step 2: Upload Files

1. Download/clone this repository
2. Upload all files to the repository:
   - `index.html`
   - `SECURITY.txt`
   - `PRIVACY.txt`
   - `LICENSE.txt`
   - `README.md`
   - Entire `assets/` folder with screenshots and icons

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** tab
3. In left sidebar, click **Pages**
4. Under "Source":
   - Branch: `main` (or `master`)
   - Folder: `/ (root)`
5. Click **Save**
6. Wait 1-2 minutes for deployment

### Step 4: Access Your Website

Your website will be live at:
```
https://<your-username>.github.io/SwiftNeo-Website/
```

---

## ⚠️ Before Public Release - CRITICAL UPDATES REQUIRED

Before making your website public, you **MUST** update these placeholders:

### 1. Update APK Download Link

In `index.html`, find:
```html
<a href="#download-apk" class="download-btn">
```

Replace `#download-apk` with your actual GitHub Releases APK link:
```html
<a href="https://github.com/softneox/SwiftNeo/releases/download/v1.0.0/SwiftNeo_v1.0.0.apk" class="download-btn">
```

### 2. Generate SHA-256 Hash

Generate the SHA-256 hash of your APK:

**Linux/Mac:**
```bash
shasum -a 256 SwiftNeo_v1.0.0.apk
```

**Windows (PowerShell):**
```powershell
Get-FileHash -Algorithm SHA256 SwiftNeo_v1.0.0.apk
```

Update the hash in `index.html` (line ~520):
```html
<div class="hash-box" id="fileHash">YOUR_ACTUAL_SHA256_HASH_HERE</div>
```

Also update in `SECURITY.txt` (line ~25).

### 3. Upload to VirusTotal

1. Go to https://www.virustotal.com
2. Upload your APK file
3. Wait for scan to complete (0/70 detections expected)
4. Copy the report URL
5. Update in `index.html` (line ~545):
```html
<a href="YOUR_VIRUSTOTAL_REPORT_URL" class="virustotal-badge">
```
6. Also update in `SECURITY.txt` (line ~32)

### 4. Extract Certificate SHA-1

Extract the signing certificate fingerprint from your APK:

**Using keytool:**
```bash
keytool -printcert -jarfile SwiftNeo_v1.0.0.apk
```

Look for "SHA1" or "SHA-1" fingerprint and update in:
- `index.html` (line ~515)
- `SECURITY.txt` (line ~20)

### 5. Replace Screenshots

Replace placeholder screenshots in `assets/screenshots/` with actual app screenshots:

- `hero.webp` - Main app screen
- `player.webp` - Video player
- `pip.webp` - Floating mini-player
- `downloads.webp` - Download manager
- `history.webp` - History screen

**Requirements:**
- Format: WebP
- Size: <150KB each
- Resolution: 1080x1920px (or similar)

### 6. Update Metadata

Update these values in `index.html`:

**Version number** (lines ~180, ~190):
```html
data-i18n="downloadBtn">⬇️ Download APK v1.0.0 (14.8 MB)
data-i18n="requirements">Android 6.0+ (API 23) • 100MB storage
```

**Scan date** (line ~542):
```html
<span data-i18n="scanDateValue">2026-02-07</span>
```

**GitHub username** (line ~145, ~785):
```html
https://github.com/<your-username>/SwiftNeo-Website
```

---

## 🎨 Customization

### Change Colors

Edit CSS variables in `index.html` (lines ~40-55):

```css
:root {
  --bg-primary: #0a0a16;           /* Background color */
  --neon-primary: #00f3ff;         /* Neon accent color */
  --neon-secondary: #7e57c2;       /* Secondary accent */
  /* ... other colors */
}
```

### Add/Remove Features

Edit the features grid in `index.html` (lines ~330-380). Each feature card:

```html
<div class="feature-card fade-in">
  <div class="feature-icon">📱</div>
  <h3 class="feature-title" data-i18n="feature2Title">Floating Mini-Player</h3>
  <p class="feature-desc" data-i18n="feature2Desc">Resizable PiP window...</p>
</div>
```

### Update Translations

All translations are in the JavaScript section (lines ~850-1150). Add new keys:

```javascript
const translations = {
  en: {
    newKey: "English text here",
    // ...
  },
  hi: {
    newKey: "हिंदी टेक्स्ट यहाँ",
    // ...
  }
};
```

Then use in HTML:
```html
<span data-i18n="newKey">Default text</span>
```

---

## 🔒 Security Best Practices

1. **Always verify APK integrity** before installing
2. **Only download from official sources** (this website or GitHub Releases)
3. **Check SHA-256 hash** matches the published value
4. **Review VirusTotal scan** before installation
5. **Keep app updated** to latest version
6. **Use on trusted devices** (avoid rooted/jailbroken devices)

---

## 📄 Legal & Compliance

### Copyright

```
SwiftNeo - Copyright © 2026 Softneox Technologies
All rights reserved.

SwiftNeo is a proprietary, closed-source application.
Unauthorized copying, modification, or distribution is prohibited.
```

### Trademarks

- **SwiftNeo** is a trademark of Softneox Technologies
- **YouTube** is a trademark of Google LLC (not affiliated with SwiftNeo)
- **Android** is a trademark of Google LLC

### DMCA Safe Harbor

SwiftNeo complies with DMCA safe harbor provisions:
- Does NOT host, store, or distribute copyrighted content
- Only provides tools for personal offline caching
- All media streamed/downloaded directly from YouTube's servers
- Users responsible for compliance with YouTube Terms of Service and copyright laws

### License

SwiftNeo is **FREE** to use but **CLOSED-SOURCE** (proprietary).

See `LICENSE.txt` for complete End-User License Agreement.

**Summary:**
- ✅ Free for personal, non-commercial use
- ✅ No payments, no subscriptions
- ❌ Not open-source (source code not available)
- ❌ No commercial use allowed
- ❌ No reverse engineering or modification

---

## 📧 Contact & Support

- **Website**: https://`<your-username>`.github.io/SwiftNeo-Website/
- **GitHub**: https://github.com/softneox/SwiftNeo-Website
- **Security Issues**: security@softneox.dev
- **Privacy Questions**: privacy@softneox.dev
- **General Support**: support@softneox.dev

---

## 📋 Documentation Files

| File | Description |
|------|-------------|
| `SECURITY.txt` | Security policy, verification methods, VirusTotal scan |
| `PRIVACY.txt` | Zero data collection policy, local storage details |
| `LICENSE.txt` | End-User License Agreement (EULA) |
| `README.md` | This file - deployment instructions |

---

## ⚠️ Important Disclaimers

### Legal Notice

**English:**
SwiftNeo is an independent application NOT affiliated with Google LLC or YouTube. It does not host, store, or distribute copyrighted content. All media is streamed/downloaded directly from YouTube's official servers. Users are solely responsible for complying with YouTube's Terms of Service and local copyright laws. This software is for PERSONAL, NON-COMMERCIAL use only.

**हिंदी:**
SwiftNeo एक स्वतंत्र एप्लिकेशन है जो Google LLC या YouTube से संबद्ध नहीं है। यह कॉपीराइट वाली सामग्री को होस्ट, स्टोर या वितरित नहीं करता। सभी मीडिया सीधे YouTube के आधिकारिक सर्वर से स्ट्रीम/डाउनलोड होता है। उपयोगकर्ता अकेले YouTube की सेवा की शर्तों और स्थानीय कॉपीराइट कानूनों का पालन करने के लिए जिम्मेदार हैं। यह सॉफ्टवेयर केवल व्यक्तिगत, गैर-वाणिज्यिक उपयोग के लिए है।

### Google Play Protect Warning

When installing SwiftNeo, you may see a warning from Google Play Protect stating "This app is not verified". This is **NORMAL** for apps not distributed via Google Play Store.

**SwiftNeo is 100% SAFE:**
- ✅ Digitally signed by Softneox Technologies
- ✅ Scanned clean on VirusTotal
- ✅ Zero malware, spyware, or adware
- ✅ Open-source dependencies only
- ✅ Privacy-focused: NO data collection

**To proceed:** Tap "Install anyway" or "Keep anyway" when prompted.

---

## 🗂️ File Checklist Before Deployment

Before making your website public, verify:

- [ ] `index.html` uploaded to repository root
- [ ] APK download link updated to actual GitHub Releases URL
- [ ] SHA-256 hash generated and updated in `index.html` and `SECURITY.txt`
- [ ] VirusTotal scan completed and report link updated
- [ ] Certificate SHA-1 fingerprint extracted and updated
- [ ] All 5 screenshots replaced with actual app screenshots (WebP format)
- [ ] Version number updated throughout `index.html`
- [ ] GitHub username updated in all links
- [ ] Scan date updated to current date
- [ ] `SECURITY.txt` uploaded
- [ ] `PRIVACY.txt` uploaded
- [ ] `LICENSE.txt` uploaded
- [ ] `README.md` uploaded
- [ ] GitHub Pages enabled (Settings → Pages)
- [ ] Website tested on mobile, tablet, and desktop browsers
- [ ] Language toggle (EN/HI) tested and working
- [ ] All links verified (no 404 errors)

---

## 📊 Performance Targets

- **File Size**: <110KB (before gzip)
- **Lighthouse Score**: >95
- **Load Time**: <2 seconds on 3G
- **Mobile Responsive**: Yes (320px → 4K)
- **Accessibility**: WCAG 2.1 AA compliant

---

## 🛠️ Technologies Used

- **HTML5** - Semantic markup
- **CSS3** - Glassmorphism theme, animations
- **Vanilla JavaScript** - Bilingual toggle, mobile menu
- **Google Fonts** - Poppins, Open Sans, Noto Sans Devanagari
- **No Frameworks** - Zero dependencies (pure vanilla)

---

## 📝 Changelog

### v1.0.0 (2026-02-07)
- Initial release
- Bilingual support (English/Hindi)
- Glassmorphic dark theme with neon accents
- SHA-256 verification section
- VirusTotal security scan integration
- Complete security & privacy documentation
- Responsive design (mobile/tablet/desktop)

---

## 📜 License

SwiftNeo is **FREE** to use but **CLOSED-SOURCE** (proprietary).

© 2026 Softneox Technologies. All rights reserved.

See `LICENSE.txt` for complete terms.

---

**Made with ❤️ by N.C. (Softneox)**

*SwiftNeo - Premium YouTube Experience. Zero Cost. Zero Ads.*