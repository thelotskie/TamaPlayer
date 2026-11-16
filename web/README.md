# Tama Player — Web

The browser companion to the Tama Player Android app. Same repository, same
name, same logo and brand purple (#884AFB, from
`app/src/main/assets/branding/`), same "no ads, no trackers" rule.

**Live (once GitHub Pages is enabled):** https://thelotskie.github.io/TamaPlayer/
served from this `web/` folder. Or just open `web/index.html` in any modern
browser — everything runs locally on your device; files you open never leave
the browser.

## What it does

- Open local video/audio files (picker or drag & drop) with a playlist queue
- Play direct stream URLs: MP4, WebM, MP3/AAC, and HLS (`.m3u8`, via hls.js;
  Safari plays HLS natively)
- Subtitles: load `.srt` / `.vtt` files (SRT is converted in-browser)
- Player controls modeled on the app: double-click sides to seek ∓10s,
  keyboard shortcuts (Space, ←/→, F, M, N/P), speed control, PiP, fullscreen
- Theme accents borrowed from the app's theme list (Default Purple,
  Catppuccin, Nord, Dracula, Tokyo Night), saved between visits
- Resume position for URL streams; Media Session (lock-screen) controls

## What it honestly cannot do (browser limits, not laziness)

A web page cannot reuse the Android app's Kotlin/libmpv code — no browser
runs it. So these stay Android-only:

- MKV/AVI and other containers browsers don't decode (libmpv plays them; a
  browser's `<video>` element does not)
- ASS/SSA styled subtitles, dual-subtitle rendering, subtitle downloads
- Anime4K and the GLSL HDR shader pipelines, torrent streaming, yt-dlp,
  Jellyfin/Navidrome clients, Google Cast, SMB/FTP browsing

If a file won't play here, that is the browser's codec list saying no — the
same file will play in the Android app.

## Files

- `index.html` — the whole player (HTML/CSS/JS, one file, hls.js from CDN)
- `logo.svg` — the app logo, copied from the app's own branding assets

License: AGPL-3.0, same as the rest of this repository (see ../LICENSE and
../UPSTREAM.md).
