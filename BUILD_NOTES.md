# Building Tama Player

Upstream build (from UPSTREAM_README.md):
  JDK 17, Android SDK, NDK 27.3.13750724, compileSdk 37
  ./gradlew :app:assembleStandardDebug     (Windows: gradlew.bat)

This VM cannot build it: Gradle/AGP dies here (daemon, ~300MB free RAM -
see AGENTS.md) and this is a full Compose + native libmpv project, far
heavier than the manual aapt2/d8 builds used for the small Tama apps.

Chosen route (2026-11-16, Othelo): GitHub Actions on the TamaPlayer repo.
.github/workflows/tama-build.yml builds an installable debug APK and stores
it as a workflow artifact. Other options if ever needed:
2. Build on Othelo's Windows PC with Android Studio / JDK 17
3. A VPS with 8GB+ RAM

Signing: create our own keystore before any public release and back it up -
losing it means users must uninstall to update (same lesson as Tama Booth).
