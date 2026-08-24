# Terms-of-Service

Public facing legal pages for Macintech LLC applications, served by GitHub Pages from `main` at
<https://macintech-llc.github.io/Terms-of-Service/>.

## Live pages

| App | Document | URL |
|---|---|---|
| Happy Home Task Tracker | Terms of Service | <https://macintech-llc.github.io/Terms-of-Service/Happy%20Home%20Task%20Tracker%20Terms%20of%20Service.html> |
| Happy Home Task Tracker | Privacy Policy | <https://macintech-llc.github.io/Terms-of-Service/happy-home-privacy-policy.html> |
| ABC SafeSpot | Privacy Policy | <https://macintech-llc.github.io/Terms-of-Service/abc-safespot-privacy-policy.html> |

These URLs are referenced from App Store Connect and from inside the apps. **Do not rename or move an
existing file** — the old URL stops resolving and the App Store listing breaks. Add new pages instead.

New pages should use lowercase, hyphenated filenames so the URL needs no percent-encoding. The Happy
Home Terms of Service predates that convention and is deliberately left as-is.

## Keeping the privacy policy accurate

The privacy policy is a legal statement about what an app actually does, and it must agree with two
other declarations:

1. the app's `PrivacyInfo.xcprivacy` manifest, and
2. the App Privacy labels published in App Store Connect.

Sources of truth per app:

| App | Manifest | Note |
|---|---|---|
| Happy Home | [`HappyHome/PrivacyInfo.xcprivacy`](https://github.com/Macintech-LLC/Happy-Home/blob/main/HappyHome/PrivacyInfo.xcprivacy) | Declares all 7 collected types; the at-a-glance table mirrors it row for row. |
| ABC SafeSpot | [`ABCSafeSpot/ABCSafeSpot/PrivacyInfo.xcprivacy`](https://github.com/Macintech-LLC/ABC-Notifier/blob/master/ABCSafeSpot/ABCSafeSpot/PrivacyInfo.xcprivacy) | ⚠ `NSPrivacyCollectedDataTypes` is currently an empty array and understates what the app collects (UDID, usage data). Sentry-collected types are covered by `Sentry.framework`'s own bundled manifest. Fix the app manifest in a future build. |

ABC SafeSpot also has a second privacy policy rendered by its own backend at
<https://abcsafespot.praeto.io/privacy-policy> (`backend/src/app/privacy-policy/page.tsx`). **Two
copies of one policy will drift.** Pick one as canonical and point the other at it.

Update this repo whenever any of the following changes in an app:

- a data type is added to or removed from `PrivacyInfo.xcprivacy`
- a data type changes between linked and not linked to identity
- a new SDK, analytics tool, or backend service begins receiving user data
- a Sentry option affecting collected data changes — for example `sendDefaultPii`,
  `attachScreenshot`, `attachViewHierarchy`, or `enableNetworkBreadcrumbs`
- account deletion, data retention, or sign-in methods change

When you change a page, bump its "Last Updated" date in the same commit.
