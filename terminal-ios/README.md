# terminal (iOS)

Minimal iOS app named `terminal` (`com.bobr.terminalpython`) with an in-app Python console UI.

## What this build does

- SwiftUI shell app
- Embedded web terminal UI
- Python execution via Pyodide runtime loaded from CDN
- GitHub Actions workflow that outputs `terminal-unsigned.ipa`

## Build `.ipa` via GitHub Actions

1. Push this folder to a GitHub repo.
2. Open `Actions` tab.
3. Run workflow: `Build terminal IPA`.
4. Download artifact: `terminal-unsigned-ipa`.

This IPA is unsigned and intended for re-signing/sideload flows (for example Scarlet).

## Local macOS build (optional)

```bash
brew install xcodegen
cd terminal-ios
xcodegen generate --spec project.yml
xcodebuild -project terminal.xcodeproj -scheme terminal -configuration Release -sdk iphoneos -destination generic/platform=iOS CODE_SIGNING_ALLOWED=NO CODE_SIGNING_REQUIRED=NO CODE_SIGN_IDENTITY="" build
```
