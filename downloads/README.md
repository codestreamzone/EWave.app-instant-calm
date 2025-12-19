# APK Download Setup

## How to Add Your APK

1. **Build the APK** on a machine with Android SDK:
   ```bash
   cd e:\EWave-app\flutter_app
   flutter build apk --release
   ```

2. **Copy the APK** to this folder:
   - The built APK will be at: `e:\EWave-app\flutter_app\build\app\outputs\flutter-apk\app-release.apk`
   - Rename it to `ewave-app.apk`
   - Copy it to this `downloads` folder

3. **Or use GitHub Actions** to build automatically:
   - Set up a workflow to build on push
   - Upload the APK as an artifact or release asset
   - Update the `APK_URL` in `index.html` to point to the GitHub release

## Alternative: Cloud Build Services

If you don't have Android SDK locally:

1. **Codemagic** (https://codemagic.io) - Free tier available
2. **GitHub Actions** - Free for public repos
3. **Bitrise** - Free tier available

## Current Configuration

The landing page is configured to download from: `downloads/ewave-app.apk`

To change this, edit the `APK_URL` in `index.html`:
```javascript
const APK_URL = 'downloads/ewave-app.apk';  // Local path
// OR
const APK_URL = 'https://github.com/yourname/ewave-app/releases/latest/download/app-release.apk';  // GitHub release
```
