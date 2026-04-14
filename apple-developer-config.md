# CladLogic Released — Apple Developer Account Configuration
# What needs to be set up in App Store Connect before submission
# Last updated: April 14, 2026

---

## 1. Certificates & Identifiers

### App ID
- **Identifier:** com.cladlogic.released
- **Description:** CladLogic Released
- **Capabilities to enable:**
  - Push Notifications (required — APNs wired in v1.9.91)
  - Associated Domains (required — Universal Links wired in v1.9.92)

### Associated Domains entitlement
Add to your Xcode project entitlements:
  applinks:released.cladlogic.com
  applinks:cladlogic-released.azurewebsites.net

### Push Notification Certificate
- Create an APNs key (preferred over certificate) in Keys section
- Key type: Apple Push Notifications service (APNs)
- Download the .p8 file — store it securely, it cannot be re-downloaded
- Note the Key ID and Team ID — both go into the iOS app's APNs configuration
- Update Program.cs AASA placeholders with real Team ID and Bundle ID before submission

---

## 2. App Store Connect — New App Setup

Go to: appstoreconnect.apple.com → My Apps → (+) New App

- **Platform:** iOS
- **Name:** CladLogic
- **Primary Language:** English (U.S.)
- **Bundle ID:** com.cladlogic.released (select from registered identifiers)
- **SKU:** CLADLOGIC-RELEASED-001
- **User Access:** Full Access

---

## 3. TestFlight Configuration

### Internal Testing
- Add up to 100 internal testers (must be App Store Connect users in your team)
- No App Review required for internal builds
- Use for initial build verification before external testing

### External Testing
- Create an external group (e.g. "Beta Testers")
- Add testers by email — they do NOT need to be in your developer account
- First external build requires App Review (usually 1–2 days)
- Recommended: invite 2–3 Cardinal Fabrication users as first external testers

### Build Requirements Before TestFlight Upload
- Xcode project must have correct Bundle ID: com.cladlogic.released
- Version: 1.0.0, Build: 1
- Signing: Automatic (Xcode manages provisioning profiles)
- Export method: App Store Connect
- Upload via Xcode Organizer or Transporter app

---

## 4. App Store Submission Checklist

Before submitting for App Review:

- [ ] App icon set added to Xcode asset catalog (all sizes generated — see icon files)
- [ ] Bundle ID matches: com.cladlogic.released
- [ ] Version 1.0.0 / Build 1 uploaded via Xcode
- [ ] All metadata filled in App Store Connect (see appstore-metadata.md)
- [ ] Privacy Policy URL set: https://cladlogic.com/privacy.html
- [ ] Support URL set: https://cladlogic.com
- [ ] Screenshots uploaded (see Section 5)
- [ ] App Privacy questionnaire completed in App Store Connect
- [ ] Review notes filled with demo credentials (see appstore-metadata.md)
- [ ] AASA placeholders replaced in Program.cs (Team ID + Bundle ID)
- [ ] APNs key configured in iOS app
- [ ] Production API URL set to: https://released.cladlogic.com

---

## 5. Screenshots Required

App Store Connect requires screenshots for each device size you support.
Minimum required sets (can use same screenshots scaled):

| Device | Size |
|--------|------|
| iPhone 6.9" (iPhone 16 Pro Max) | 1320 x 2868 px |
| iPhone 6.5" (iPhone 14 Plus) | 1242 x 2688 px |
| iPad Pro 13" (M4) | 2064 x 2752 px |

Notes:
- iPad screenshots only required if app supports iPad
- Screenshots can be device frames or pure UI — Apple accepts both
- Promotional text overlay on screenshots is allowed
- Minimum 3, maximum 10 per device size

---

## 6. Age Rating

Complete the age rating questionnaire in App Store Connect:
- All categories: None / No
- Result: **4+**

---

## 7. Export Compliance

- Uses HTTPS (standard encryption): **Yes**
- Uses encryption beyond standard HTTPS: **No**
- Answer: **No** to export compliance questions — standard HTTPS only qualifies for exemption

---
