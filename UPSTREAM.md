# Upstream provenance

Tama Player is a fork. It is NOT written from scratch.

- Copied from: https://github.com/Riteshp2001/mpvRx
- Upstream commit: a93802daa049ffdbd5bb80102f68a41467798f34 (master, copied 2026-11-16)
- Upstream version at copy time: 3.0.2.1 (releaseVersionCode 303)
- Lineage: mpv-android / libmpv -> mpvKt -> mpvEx (marlboro-advance) -> mpvRx (Riteshp2001) -> Tama Player (Othelo / thelotskie)
- License: GNU AGPL-3.0 (see LICENSE, unchanged). This fork must stay AGPL-3.0,
  keep upstream copyright/credit notices, and publish its source the same way.
- Native mpv library: app.gyrolet.mpvlib, from https://github.com/Riteshp2001/mpvlibAndroid

Internal Kotlin namespace stays `app.gyrolet.mpvrx` in v1.0.0 on purpose:
renaming it means rewriting every package/import in ~1,300 files plus the
Room schema, Cast provider and native glue, for zero user-visible gain.
What the user sees and what Android installs is ours: applicationId
`com.tama.player`, name "Tama Player", our version band, our update feed.
