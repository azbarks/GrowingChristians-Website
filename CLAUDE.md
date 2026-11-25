# Growing Christians Website — Claude Context

Static download / help site for the Growing Christians apps (iPhone: `../GrowingChristians`,
Android: `../GrowingChristians-Android`). Same pattern as `../bookit_website`: plain HTML + one
shared `style.css`, no build step, no JavaScript. Intended for GitHub Pages as repo
**GrowingChristians-Website** → https://azbarks.github.io/GrowingChristians-Website

**Not public yet.** The talks and the "Growing Christians" name belong to Growing Christians
Ministries; Bruce is asking the ministry (a friend) before publishing. Keep the "independent
listener's app" disclaimer on every page.

## Pages
- `index.html` — hero (Talks tab screenshot), feature cards, **Download** (`#download`):
  Android = `downloads/GrowingChristians.apk`; iPhone = request a TestFlight invite by email.
- `help.html` — the full guide, sidebar sections. Keep in step with both apps' behavior.
- `privacy.html` — no data collected; only network = growingchristians.org / media.growingchristians.org
  (audio stream/download + page lookup). Update if the apps add any network call or permission.
- `style.css` — green palette from the app (`--accent #2E7D4A`, icon bg `#00382B`), Bitter + Source Sans 3, light + dark.
- `images/` — icon/favicon/apple-touch-icon from the iOS AppIcon; `shot-*.png` iPhone simulator screenshots.

## Updating the Android download
Copy the newest APK over `downloads/GrowingChristians.apk` (same name, so links don't change):
`cp ../GrowingChristians-Android/dist/GrowingChristians-Android-1.0-vN.apk downloads/GrowingChristians.apk`
It is debug-signed. Updates install over it only while signed with the same key (this Mac's
`~/.android/debug.keystore`) — before a wide release, switch to a proper release key (and then
everyone reinstalls once).

## Keep accurate
- iPhone needs iOS 26+ (deployment target 26.4) — change help.html if that's lowered. Android 8+.
- Behaviors described: listen counted only at end of playback; Mark as Heard (date); remove a date
  (swipe on iPhone, × on Android); iPhone book swipes (right = Heard It, left = Play); speed 0.75–2×;
  ⟲15 / 30⟳; downloads (talk row, book menu, Manage Downloads, auto-remove default ON, iPhone pauses
  downloads in background); Start Over keeps history; backup merges, works iPhone ⇄ Android;
  history only on the phone (Android auto-backup is off since versionCode 5).
