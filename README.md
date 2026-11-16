# Tama Player

**Tama Player** - a powerful, feature-packed Android video & music player based on libmpv.
No ads. No trackers. Forked from mpvRx by Othelo (thelotskie), built by Tama.

> This is a fork, not a from-scratch app. Full credit and provenance: see UPSTREAM.md.
> Licensed AGPL-3.0, same as upstream - see LICENSE.

## What it plays / does (inherited from mpvRx 3.0.2.1)
- Local video & music libraries, SMB / FTP / WebDAV, direct streams, HLS
- HDR shader pipeline (83 GLSL shaders), Anime4K upscaling, ambient mode
- Full gesture system: double-tap seek, swipe seek/volume/brightness, pinch zoom, subtitle drag
- Dual subtitles, online subtitle search, styling, speech-to-subtitle
- Jellyfin client, Navidrome/Subsonic music, audiobooks, lyrics (LRCLIB)
- Google Cast, PiP, background playback, Syncplay, torrent streaming (sideload builds)
- 25+ themes incl. AMOLED black, Material 3 Expressive UI
- yt-dlp streaming (YouTube/Twitch/etc.) in sideload builds

## Our changes
See OUR_CHANGES.md - new name, new package (com.tama.player), own version
band, own update feed.

## Build
See BUILD_NOTES.md - needs GitHub Actions, a Windows PC, or a bigger box;
this workspace VM cannot run its Gradle build.
