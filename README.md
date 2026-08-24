# Terms-of-Service

Public facing legal pages for Macintech LLC applications, served by GitHub Pages from `main` at
<https://macintech-llc.github.io/Terms-of-Service/>.

## Live pages

| App | Document | URL |
|---|---|---|
| Happy Home Task Tracker | Terms of Service | <https://macintech-llc.github.io/Terms-of-Service/Happy%20Home%20Task%20Tracker%20Terms%20of%20Service.html> |
| Happy Home Task Tracker | Privacy Policy | <https://macintech-llc.github.io/Terms-of-Service/happy-home-privacy-policy.html> |

These URLs are referenced from App Store Connect and from inside the apps. **Do not rename or move an
existing file** — the old URL stops resolving and the App Store listing breaks. Add new pages instead.

New pages should use lowercase, hyphenated filenames so the URL needs no percent-encoding. The Happy
Home Terms of Service predates that convention and is deliberately left as-is.

## Keeping the privacy policy accurate

The privacy policy is a legal statement about what an app actually does, and it must agree with two
other declarations:

1. the app's `PrivacyInfo.xcprivacy` manifest, and
2. the App Privacy labels published in App Store Connect.

For Happy Home, the source of truth is
[`HappyHome/PrivacyInfo.xcprivacy`](https://github.com/Macintech-LLC/Happy-Home/blob/main/HappyHome/PrivacyInfo.xcprivacy).
The "What We Collect, at a Glance" table in the privacy policy mirrors it row for row.

Update this repo whenever any of the following changes in an app:

- a data type is added to or removed from `PrivacyInfo.xcprivacy`
- a data type changes between linked and not linked to identity
- a new SDK, analytics tool, or backend service begins receiving user data
- a Sentry option affecting collected data changes — for example `sendDefaultPii`,
  `attachScreenshot`, `attachViewHierarchy`, or `enableNetworkBreadcrumbs`
- account deletion, data retention, or sign-in methods change

When you change a page, bump its "Last Updated" date in the same commit.
