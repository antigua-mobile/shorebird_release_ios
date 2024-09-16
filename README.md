# Shorebird Release iOS
GitHub action for convenient usage of the shorebird-release action.

## Involved steps
1. Installs the signing certificate into the keychain
2. Copies the provisioning profile to the expected location.

## Usage
Add the following step to your GitHub Actions workflow (example):

```yaml
- name: Setup iOS signing certificate and provisioning profile
  uses: antigua-mobile/ios_signing_certificate_and_profile_setup@v1.0
- name: Build Shorebird iOS release
        uses: antigua-mobile/shorebird_release_ios
        with:
          app_flavor: staging
          export_options_plist: ios/ExportOptions_Staging.plist
          flutter_args: --dart-define=API_BASE_URL=${{ vars.STAGING_API_BASE_URL }}
          shorebird_token: ${{ secrets.SHOREBIRD_TOKEN }}
```