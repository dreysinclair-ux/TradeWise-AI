TRADEWISE AI - MOBILE (ANDROID + iPHONE)

One codebase: a mobile web app in www/ wrapped with Capacitor to make real Android and iOS apps.
Same features as the Windows version: chart scanner (OpenAI, Google Gemini, OpenRouter with model picker),
academy, calculators, journal, preview. Differences: the journal is saved on the device, and the AI key can
optionally be remembered (off by default). Educational tool only - not financial advice.

------------------------------------------------------------
OPTION A - ANDROID APK WITHOUT INSTALLING ANYTHING (easiest)
------------------------------------------------------------
1. Create a free GitHub account and a new empty repository.
2. Upload ALL files from this folder (including the hidden .github folder) to the repository.
   (Easiest: install GitHub Desktop, add this folder, commit and push.)
3. On GitHub open the Actions tab -> "Build Android APK" -> Run workflow.
4. After a few minutes, open the finished run and download the "TradeWiseAI-debug-apk" artifact (a zip
   containing app-debug.apk).
5. Copy app-debug.apk to your Android phone and open it. Allow "Install unknown apps" when asked.
   (This is a debug build for personal use. Publishing on Google Play needs a signed release build.)

------------------------------------------------------------
OPTION B - ANDROID, BUILD ON YOUR OWN PC
------------------------------------------------------------
Needs Node.js 22+, JDK 21 and Android Studio.
  npm install
  npx cap add android
  npx capacitor-assets generate --android
  npx cap sync android
  npx cap open android      (then Build > Build APK in Android Studio)

------------------------------------------------------------
IPHONE
------------------------------------------------------------
A real iOS app can only be built on a Mac with Xcode (and an Apple developer account to install on a device
or publish):
  npm install
  npx cap add ios
  npx capacitor-assets generate --ios
  npx cap sync ios
  npx cap open ios

No Mac? Use it as a home-screen web app instead: host the www folder on any HTTPS static host (GitHub Pages,
Netlify, Cloudflare Pages), open the link in Safari, tap Share -> Add to Home Screen.
NOTE: in a browser, AI providers must allow cross-origin requests from your site. OpenAI, Gemini and
OpenRouter generally do, but if a provider blocks it, use the Android/iOS app builds above, which send
requests natively.

------------------------------------------------------------
KEYS AND SAFETY
------------------------------------------------------------
- Paste only the key itself. Gemini keys start with AIza or AQ, OpenAI keys with sk-.
- The key is kept in memory only unless you tick "Remember this key on this device". Remembered keys are stored
  unencrypted in the app's storage - do not tick this on a shared phone.
- Set a low spending limit on any key you create, and never share a key in chat or screenshots.
- A screenshot analysis can be wrong. BUY/SELL are conditional educational assessments, not instructions.
