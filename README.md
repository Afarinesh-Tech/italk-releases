# italk-releases

Public update channel for the **iTalk** Android app (`com.nouralzahra.italk`).

- `version.json` — the update manifest the app polls on launch
  (raw URL: `https://raw.githubusercontent.com/Afarinesh-Tech/italk-releases/main/version.json`)
- APKs — attached as assets to [GitHub Releases](../../releases), one release per version
  (`v<versionName>` tag, asset named `italk-<versionName>.apk`)

## Manifest format

```json
{
  "latestVersionCode": 3090900,
  "latestVersionName": "3.9.9",
  "minVersionCode": 3090900,
  "apkUrl": "https://github.com/Afarinesh-Tech/italk-releases/releases/download/v3.9.9/italk-3.9.9.apk",
  "message": "changelog shown in the update dialog (supports Persian)"
}
```

`minVersionCode` — builds older than this get a **forced**, non-dismissible update.

## Publishing a release

Build and sign the release APK in the app repo, then run
[`scripts/publish-release.sh`](https://github.com/Afarinesh-Tech/italk-android/blob/main/scripts/publish-release.sh)
from the app repo — it uploads the APK as a GitHub release here and updates
`version.json` in one step. This repo must stay **public**: the app fetches the
manifest and APK unauthenticated.
