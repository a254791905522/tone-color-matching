# Tone Color Matching - Publish Checklist

## 1. Project Configuration
- [x] Bundle ID contains 'rosewood': com.rosewood.tonecolormatching.game
- [x] TARGETED_DEVICE_FAMILY: "1" (iPhone only) at target level
- [x] No iPad support (UIDeviceFamily = 1 only)
- [x] project.yml has no hardcoded signing restrictions
- [x] DEVELOPMENT_TEAM empty (uses Xcode Signing & Capabilities selection)
- [x] CODE_SIGN_STYLE: Automatic
- [x] MARKETING_VERSION: "1.0"
- [x] CURRENT_PROJECT_VERSION: "1"
- [x] Deployment target: iOS 15.0

## 2. Info.plist
- [x] CFBundleDisplayName: "Tone Color Matching"
- [x] CFBundleIconName: "AppIcon"
- [x] ITSAppUsesNonExemptEncryption: false
- [x] UILaunchStoryboardName: "LaunchScreen"
- [x] UIRequiredDeviceCapabilities: arm64
- [x] UISupportedInterfaceOrientations: UIInterfaceOrientationPortrait only

## 3. App Icon
- [x] AppIcon.appiconset has all required sizes (12 icons: 8 iPhone + 3 iPad + 1 marketing)
- [x] 1024x1024 marketing icon: no Alpha channel (RGB PNG)
- [x] All icons: no Alpha channel (RGB)
- [x] Contents.json complete and valid

## 4. Launch Screen
- [x] LaunchScreen.storyboard root tag is `<document>` (lowercase)
- [x] No references to non-existent images
- [x] Shows game title "Tone Color Matching" and subtitle "Match the World's Colors"

## 5. Debug UI
- [x] showsFPS: NO (not set)
- [x] showsNodeCount: NO (not set)

## 6. Template Residue
- [x] No tw_* assets
- [x] No game_01_* assets (deleted: anchor, ball, bg_main, cube, fragment, obstacle, portal)
- [x] No Template assets
- [x] No Backgrounds.imageset residue (deleted empty imageset that was only used by old LaunchScreen)
- [x] All class prefixes are BHQ, all persistence keys are BHQ*

## 7. Screenshots
- [x] screenshots_65/ (1284x2778, 6.5" display) - 4 screenshots (01_menu, 02_game1, 03_game2, 04_game-success)
- [x] screenshots_55/ (1242x2208, 5.5" display) - 4 screenshots (01_menu, 02_game1, 03_game2, 04_game-success)
- [x] All screenshots: no Alpha channel (RGB mode)
- [x] Screenshots show real gameplay

## 8. Release Project
- [x] ToneColorMatching-ReleaseProject/ created
- [x] Sources synced (SpriteKitGameFramework with BHQ* classes)
- [x] Unused old source files excluded (AppDelegate, ViewController, main.m from SpriteKitGameFramework)
- [x] project.yml synced (no signing restrictions)
- [x] xcodegen generate successful
- [x] Info.plist has arm64 (not armv7)
- [x] TARGETED_DEVICE_FAMILY = 1 only in .xcodeproj

## 9. Publish Files
- [x] index.html (uses screenshots_65/ images, /privacy.html link)
- [x] privacy.html (offline, no data collection)
- [x] keywords.txt (77 chars, under 100 limit)
- [x] README.md
- [x] GAMEPLAY_FACT_CARD.md
- [x] PUBLISH_CHECKLIST.md (this file)
- [x] appstore-review-text.html (Format 3: .field + label + pre.value)
- [x] vercel.json (cleanUrls: false)
- [x] .gitignore

## 10. Archive Build
- [ ] xcodebuild archive with CODE_SIGNING_ALLOWED=NO - ARCHIVE SUCCEEDED
- [ ] Verify .app contains: Assets.car, AppIcon*.png, LaunchScreen.storyboardc
- [ ] Verify CFBundleIdentifier = com.rosewood.tonecolormatching.game
- [ ] Verify CFBundleDisplayName = Tone Color Matching
- [ ] Verify UIDeviceFamily = 1

## 11. GitHub/Vercel Deployment
- [ ] Push publish/ToneColorMatching/ to GitHub (gh account: a254791905522, repo: tone-color-matching)
- [ ] Use proxy 127.0.0.1:7897
- [ ] Vercel deployed: https://tone-color-matching.vercel.app
- [ ] curl verify index.html live (HTTP 200)
- [ ] curl verify /privacy.html live (HTTP 200, no 308 redirect)

## 12. App Store Connect
- [ ] App name: Tone Color Matching
- [ ] Subtitle: Match the World's Colors
- [ ] Bundle ID: com.rosewood.tonecolormatching.game
- [ ] SKU: tonecolormatching-ios-001
- [ ] Support URL: https://tone-color-matching.vercel.app
- [ ] Privacy Policy URL: https://tone-color-matching.vercel.app/privacy.html
- [ ] Screenshots uploaded (1284x2778 and 1242x2208)
- [ ] Keywords from keywords.txt
- [ ] Description from appstore-review-text.html
- [ ] Reviewer: Evans Omondi (Last: Omondi / First: Evans)
- [ ] Phone: +1 2096550297
- [ ] Email: croitorzamkov@gmail.com

## 13. Validation
- [ ] validate_appstore_review_text.py: ALL CHECKS PASSED

## 14. Notes
- Sound/Music/Haptics toggles exist in Settings (BHQSaveManager has soundEnabled, musicEnabled, hapticsEnabled)
- 50 flag color levels across 5 regions (Asia, Europe, Americas, Oceania, Africa)
- HSL color model: Hue (0-360), Saturation (0-100%), Lightness (0-100%)
- Scoring via DeltaE (CIE color difference)
- 30-second time limit per level
- Difficulty 1-5, scaling every 10 levels
- Levels 1-5 show target preview, levels 1-10 show hints, levels 11+ are pure memory
