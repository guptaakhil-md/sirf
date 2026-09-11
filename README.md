# The Sirf website

Three files. Upload all three, exactly as they are, to any static host.

- `index.html`   the page
- `Sirf-release.apk`   the app (copy the newest one here after every build)
- `version.json`   what the app reads to know whether an update is required

## Putting it on GitHub Pages (free)

1. Sign in at github.com and create a new repository. Name it `sirf`. Public.
   Do not add a README.
2. On the empty repository page, choose "uploading an existing file". Drag in
   the three files above. Commit.
3. Repository Settings, then Pages in the left menu. Under "Build and
   deployment" set Source to "Deploy from a branch", branch `main`, folder
   `/ (root)`. Save.
4. Wait a minute, reload the Pages settings. It shows the address:
   `https://guptaakhil-md.github.io/sirf/`

5. Open `version.json` in the repository, edit it, and replace
   `guptaakhil-md` in `apkUrl` with your real GitHub username. Commit.
6. Give the address to Akhil's build so it goes into the app:
   `https://guptaakhil-md.github.io/sirf/version.json` is the value for
   `UPDATE_URL` in android/.../MainActivity.kt. Rebuild, then upload the new
   `Sirf-release.apk` over the old one (step 2 again, it replaces).

Only after step 6 should the APK be shared with anyone.

## Pushing an update later

1. Upload the new `Sirf-release.apk` over the old one.
2. Edit `version.json`: raise `minVersionCode` to the new version code and
   `versionName` to the new version name.

APK first, number second.

## Never put here

The signing key, `keystore.properties`, or anything from the `important`
folder except the APK and `version.json`. This repository is public.
