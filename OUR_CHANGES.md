# Tama Player - changes vs upstream mpvRx (v1.0.0, 2026-11-16)

## Identity
- App name: mpvRx -> Tama Player (strings.xml app_name + 23 user-visible strings, fastlane title)
- applicationId: app.gyrolet.mpvrx / com.gyrolet.mpvrx -> com.tama.player (all flavors)
  Installs side-by-side with the original; separate data, no clash.
- rootProject.name: mpvRx -> TamaPlayer
- Version: reset to our own band - versionName 1.0.0, releaseVersionCode 1

## Behaviour
- Self-update now checks github.com/thelotskie/TamaPlayer releases, NOT upstream.
  (Upstream's updater would have silently replaced Tama Player with stock mpvRx.)
  Until that repo has a release, the check simply finds no update.
- Lyrics provider user-agent identifies as TamaPlayer, crediting upstream.

## Kept on purpose (AGPL-3.0 + honesty)
- LICENSE unchanged; upstream README preserved as UPSTREAM_README.md
- About / Hall of Fame / contributors still credit mpvRx, mpvEx, mpvKt and mpv authors
- github_repo_url string still points at upstream until our repo is published
- Internal namespace app.gyrolet.mpvrx unchanged (see UPSTREAM.md)

## NOT done yet - needs Othelo's pick
- App icon / splash: still upstream purple play icon (assets in app/src/main/res/mipmap-*)
- Default theme/accent: upstream ships 25+ themes, purple default - can set our own default
- Feature trims: torrent streaming, Jellyfin, Navidrome, AI subtitles, yt-dlp all still in
- A real APK build: see BUILD_NOTES.md

## Cloud build setup (2026-11-16)
- Added .github/workflows/tama-build.yml: builds :app:assembleStandardDebug on
  push to master (app paths only) or on demand; uploads the installable debug APK
  as the TamaPlayer-debug-apk artifact. No secrets needed.
- Upstream build.yml: removed its push-to-master trigger (5-flavor release
  matrix, signs only when SIGNING_* secrets exist) - now PR/manual only.
- Upstream preview.yml: DELETED. It ran every 30 minutes and published to the
  upstream author's GitHub Pages site (riteshp2001.github.io/mpvRx).
- Upstream release.yml: kept, tag-triggered; needs SIGNING_* secrets before use.
