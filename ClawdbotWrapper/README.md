# Clawdbot WebView APK Wrapper

Android WebView wrapper for:

https://clawdbotatg.eth.link/

## Navigation behavior

This version keeps all HTTPS page navigations inside the app WebView. This is useful when the site depends on redirects or pages from multiple HTTPS domains.

Blocked or external behavior:

- `http://` main-frame navigation is blocked.
- `file:`, `content:`, `javascript:`, and unknown schemes are blocked for main-frame navigation.
- Wallet/deep-link/user-action schemes such as `wc:`, `metamask:`, `trust:`, `intent:`, `market:`, `mailto:`, `tel:`, and `sms:` are handed off to Android.

## Security posture

The wrapper hardens the Android WebView but does not secure the remote website itself.

Controls enabled:

- HTTPS-only network policy
- Cleartext traffic disabled
- SSL errors cancelled
- Mixed content blocked
- Safe Browsing enabled
- WebView debugging disabled
- File/content access disabled
- Universal file URL access disabled
- Geolocation disabled
- Third-party cookies disabled
- App backup/data extraction disabled
- Renderer crash handling
- WebView cleanup on destroy
- Release shrink/minify enabled

## Build

PowerShell:

```powershell
cd C:\Users\MicroAple\Documents\GitHub\CLAWDBOTATG\ClawdbotWrapper
.\gradlew.bat assembleDebug
```

Android Studio:

```text
File → Open → ClawdbotWrapper
Build → Build Bundle(s) / APK(s) → Build APK(s)
```

APK output:

```text
app/build/outputs/apk/debug/app-debug.apk
```
