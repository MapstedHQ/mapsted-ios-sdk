# Mapsted iOS SDK

Official binary distribution of the **Mapsted Mobile SDK for iOS** — indoor positioning,
blue-dot location, wayfinding, maps, and location-based marketing, with no external hardware.

**Current release: `26.6.1`**

> 📘 **Full documentation, guides, and API reference live on the Mapsted Developer site:**
> **https://developer.mapsted.com/mobile-sdk/**

---

## What's in this repository

This repository hosts the prebuilt **XCFramework** binaries for the iOS SDK as
[GitHub Release](https://github.com/MapstedHQ/mapsted-ios-sdk/releases) assets. Each release tag
(e.g. [`26.6.1`](https://github.com/MapstedHQ/mapsted-ios-sdk/releases/tag/26.6.1)) carries one
`.xcframework.zip` per module.

Every binary is a **universal XCFramework** containing both device (`ios-arm64`) and
simulator (`ios-arm64_x86_64-simulator`) slices — so a **single source works for both device and
simulator builds**. No separate simulator feed is required.

| Pod | Framework |
|-----|-----------|
| `mapsted-sdk-core` | `MapstedCore.xcframework` |
| `mapsted-sdk-map` | `MapstedMap.xcframework` |
| `mapsted-sdk-map-ui` | `MapstedMapUi.xcframework` |
| `mapsted-sdk-ui-components` | `MapstedComponentsUI.xcframework` |
| `mapsted-sdk-components-core` | `MapstedComponentsCore.xcframework` |
| `mapsted-sdk-alerts` | `MapstedAlerts.xcframework` |
| `mapsted-sdk-triggers-core` | `MapstedTriggersCore.xcframework` |
| `mapsted-sdk-topbar-notification` | `MapstedTopBarNotification.xcframework` |
| `mapsted-sdk-location-share` | `MapstedLocationShare.xcframework` |
| `mapsted-sdk-loc-marketing` | `LocationMarketing.xcframework` |
| `mapsted-sdk-app-template` | `AppTemplate.xcframework` |

The Carto base-map dependency (`mapsted-sdk-core-map`) is distributed separately and resolves
automatically as a transitive dependency.

---

## Requirements

| | |
|---|---|
| Xcode | 26.3+ |
| iOS deployment target | 16.0+ |
| Swift | 5 (minimum language mode) |
| CocoaPods | 1.8+ |

---

## Installation (CocoaPods)

Add the Mapsted spec repository and CocoaPods' CDN as sources at the top of your `Podfile`:

```ruby
source 'https://github.com/MapstedHQ/podspec.git'
source 'https://cdn.cocoapods.org/'

platform :ios, '16.0'
use_frameworks!

target 'YourApp' do
  pod 'mapsted-sdk-core',    '~> 26.6.1'
  pod 'mapsted-sdk-map',     '~> 26.6.1'
  pod 'mapsted-sdk-map-ui',  '~> 26.6.1'
  # add the other modules you need (see the table above)
end
```

Then:

```bash
pod install --repo-update
```

Open the generated `.xcworkspace` (not the `.xcodeproj`).

> The universal XCFrameworks work for **both device and simulator** from this single source —
> there is no longer a separate simulator feed.

Full step-by-step setup, licence-key configuration, and initialization code:
**https://developer.mapsted.com/mobile-sdk/getting-started/ios-getting-started/**

---

## Installation (Swift Package Manager)

The SDK is also available as a Swift package. In Xcode: **File → Add Package Dependencies…**, enter:

```
https://github.com/MapstedHQ/mapsted-ios-sdk-spm
```

Set the rule to **Up to Next Major Version** starting at **26.6.1**, then add the products you need
(most map apps add **MapstedMapUi**; positioning-only apps add **MapstedCore**). Each module is a
universal XCFramework (device **and** simulator in one), so there is no separate simulator setup.

Full setup + licence-key steps:
**https://developer.mapsted.com/mobile-sdk/getting-started/ios-getting-started/**

---

## Release notes

- **26.6.1** — https://developer.mapsted.com/mobile-sdk/release-notes/#v2661
- All releases — https://developer.mapsted.com/mobile-sdk/release-notes/

---

## Documentation & support

- 🏠 Developer site — https://developer.mapsted.com/mobile-sdk/
- 🚀 Getting started (iOS) — https://developer.mapsted.com/mobile-sdk/getting-started/ios-getting-started/
- 📖 API reference — https://developer.mapsted.com/mobile-sdk/api-reference/documentation/mapstedcore/
- 📝 Release notes — https://developer.mapsted.com/mobile-sdk/release-notes/
- ✉️ Support — https://mapsted.com/contact-us

---

© Mapsted Corp. All rights reserved.
