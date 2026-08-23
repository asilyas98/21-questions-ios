# 21 Questions — iOS

This is the iOS App Store version of 21 Questions, built with Capacitor.

## How the build works

Push to `main` → GitHub Actions runs on a Mac in the cloud → produces a signed `.ipa` → download it → upload to App Store Connect via Transporter.

## GitHub Secrets required

| Secret | What it is |
|--------|-----------|
| `APPLE_DIST_CERTIFICATE` | Apple Distribution certificate (.p12), base64 encoded |
| `APPLE_DIST_CERTIFICATE_PASSWORD` | Password for the .p12 |
| `APPLE_PROVISIONING_PROFILE` | App Store provisioning profile (.mobileprovision), base64 encoded |
| `APPLE_TEAM_ID` | Your 10-character Team ID from developer.apple.com |

## Getting the certificates

1. Go to developer.apple.com → Certificates → create an **Apple Distribution** certificate
2. Download it, double-click to install in Keychain
3. In Keychain Access → right-click → Export as .p12 → set a password
4. Base64 encode it: `certutil -encode cert.p12 cert.txt` (Windows) or `base64 -i cert.p12` (Mac)

## Getting the provisioning profile

1. developer.apple.com → Profiles → New → App Store → select your App ID → select your Distribution cert
2. Download the `.mobileprovision` file
3. Base64 encode it the same way as the certificate
