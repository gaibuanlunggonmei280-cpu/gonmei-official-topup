# Gonmei Official Topup — Android-ready Flutter starter

A dark-premium Flutter starter for Gonmei Official Topup.

## Included
- Home, Games, Orders and Account tabs
- PUBG / BGMI UC, Mobile Legends Diamonds, Clash of Clans and Other Games
- Package selection and Player ID entry
- Demo order list (stored only in app memory)
- INR store configuration and support contact supplied by the owner
- Android build instructions and a helper script

## Build an Android APK

### Requirements
- A computer running Windows, macOS or Linux (an iPhone alone cannot compile this project).
- Flutter SDK installed and added to PATH.
- Android Studio installed, including Android SDK and Android build tools.
- Run `flutter doctor` and resolve the Android toolchain issues it reports.

### Commands
From this project folder:

```bash
flutter create --platforms=android --org com.gonmei .
flutter pub get
flutter analyze
flutter test
flutter build apk --release
```

The APK will be generated at:

`build/app/outputs/flutter-apk/app-release.apk`

Copy that APK to an Android phone and open it to install. If Android blocks installation, allow your file manager/browser to install unknown apps for this APK, then turn that permission off again afterward. You may need to sign the app with your own release key before distributing it publicly.

A helper script is included:
- Windows: `build_android.bat`
- macOS/Linux: `build_android.sh`

## iPhone build

iOS builds require macOS, Xcode, and Apple signing configuration. On a Mac, create the iOS platform and run:

```bash
flutter create --platforms=ios --org com.gonmei .
flutter pub get
flutter build ipa --release
```

## Important limitations

This is a front-end/demo app, not yet a live top-up business system:
- Prices are placeholders and must be configured.
- The demo order list is in-memory and clears when the app restarts.
- No payment is collected; UPI and gateway choices are only preferences in the demo UI.
- No game currency is delivered automatically.

Before real launch, add a backend (for example Firebase), secure customer authentication, server-created payment orders, signed payment webhooks, an authorized supplier API for each game, protected admin access, refunds/reconciliation, privacy policy, terms, refund policy and store listing assets. Never place payment secrets or supplier API keys in the mobile app. The backend must verify payment and supplier fulfilment before an order is marked paid or delivered.

## Owner-provided configuration
- App: Gonmei Official Topup
- Currency: INR (₹)
- Intended payments: UPI + payment gateway
- Intended fulfilment: automatic (requires authorized supplier API integration)
- Support contact: 9233170503
