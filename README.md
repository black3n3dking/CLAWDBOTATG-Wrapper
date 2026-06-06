```text
README.md
```

````md
# CLAWDBOTATG Android Wrapper

CLAWDBOTATG Android Wrapper is a lightweight Android WebView application that opens the CLAWDBOTATG web app inside a native Android APK shell.

The app is designed for simple installation, direct access, and a cleaner mobile experience without requiring users to manually open the website in a browser.

## Target Website

```text
https://clawdbotatg.eth.link
````

## Features

* Android WebView wrapper
* Loads the CLAWDBOTATG web app directly
* Keeps HTTPS links inside the app
* Blocks unsafe non-HTTPS web navigation
* Handles wallet/deep links externally when required
* JavaScript enabled for modern web app support
* DOM storage enabled
* Mixed content blocked
* File and content access disabled
* WebView debugging disabled
* Safe Browsing enabled where supported
* Minimal Android permissions
* No backend required
* No user tracking added by the wrapper

## Security Model

This APK is a wrapper around the public CLAWDBOTATG web app.

The wrapper applies basic Android WebView hardening:

* HTTPS-only web navigation
* No arbitrary file access
* No universal file URL access
* No WebView debugging in production
* No unnecessary dangerous permissions
* Unsafe schemes are blocked or handed off externally
* Remote content remains controlled by the website itself

Security of the remote website, loaded scripts, ENS/IPFS gateway behavior, wallet interactions, and third-party web dependencies is outside the control of this Android wrapper.

## Build Requirements

* Android Studio
* Android SDK
* JDK 17 or newer recommended
* Gradle / Android Gradle Plugin configured by Android Studio

## Build Debug APK

Open the project in Android Studio:

```text
File → Open → ClawdbotWrapper
```

Then build:

```text
Build → Build Bundle(s) / APK(s) → Build APK(s)
```

Or from terminal, if Gradle wrapper exists:

```powershell
.\gradlew.bat assembleDebug
```

Debug APK output:

```text
app/build/outputs/apk/debug/app-debug.apk
```

## Install Debug APK

With USB debugging enabled on an Android device:

```powershell
adb install app/build/outputs/apk/debug/app-debug.apk
```

## Release APK

For public distribution, build a signed release APK.

Do not commit signing keys, keystores, passwords, service account files, wallet keys, or private credentials to this repository.

Use GitHub Releases for APK distribution instead of committing APK files directly into the source tree.

## Repository Safety

This repository should contain only source code and public configuration.

Do not commit:

* `.env` files
* `local.properties`
* signing keys
* keystores
* API tokens
* wallet private keys
* seed phrases
* Play Console credentials
* Firebase service account files
* Cloud provider credentials

## License

Add your chosen license here.

````

Short GitHub release APK description:

```md
## CLAWDBOTATG Android Wrapper APK

This release provides an Android APK wrapper for:

```text
https://clawdbotatg.eth.link
````

The app opens CLAWDBOTATG inside a hardened Android WebView and keeps HTTPS navigation inside the app while blocking unsafe schemes.

### Notes

* This is a WebView wrapper, not a separate native backend.
* The APK does not include private keys, wallet credentials, or backend secrets.
* Security of the remote website and third-party web content remains outside the wrapper.
* Install manually by downloading the APK and allowing installation from trusted sources.

````

Short one-line release description:

```text
Android WebView APK wrapper for CLAWDBOTATG, loading https://clawdbotatg.eth.link with HTTPS-only in-app navigation and basic WebView hardening.
````
