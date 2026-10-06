AG-ID — iOS App Store build package (Capacitor wrapper)

What this is
- A native iOS shell (Apple requires this) that opens https://ag-id.com.au full-screen.
- Bundle ID: au.com.ag-id.app   Version: 1.0 (Build 1)
- Icons, launch screen and encryption exemption are already configured.

How it gets built and sent to Apple (needs an Apple build machine — we use Codemagic's cloud Macs):

1. Put this folder in a GitHub repository (free account → "New repository" → "Upload files" → drag the contents of this folder in).
2. Sign up at codemagic.io with that GitHub account.
3. In Codemagic: Add application → choose the repo → set workflow to iOS.
4. Code signing: choose "Automatic" and let Codemagic create the distribution certificate/profile with your Apple Developer account (it signs in via App Store Connect).
5. Publishing: add an App Store Connect connection (App Store Connect → Users and Access → Integrations → generate an API key, give Codemagic the key ID, issuer ID and the .p8 file).
6. Start the build — when it succeeds it uploads straight to App Store Connect as Build 1, and it appears on your 1.0 submission page within ~10-15 minutes.
7. Back in App Store Connect: select the build in the Build section, then click "Add for Review" / "Submit for Review".
