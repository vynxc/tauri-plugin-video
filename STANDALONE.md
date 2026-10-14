# Standalone checkpoint

The experimental branch separates the native Tauri playback plugin from the
application. Its personal-account repository name is `vynxc/tauri-plugin-video`;
the older `vynxc/tauri-video-plugin` URL currently redirects to the upstream
`get-air/tauri-video-plugin` repository, so that redirect is preserved.

The JavaScript namespace is `@vynxc/video-tauri`. Package/crate version `0.4.0`
and native protocol `1` are unchanged. Qualification and internal runtime labels
use `TAURI_VIDEO_`/`tauri-video` rather than a product identity. Original MIT and
Apache-2.0 licenses and Git history remain intact.

Local evidence: 31 JavaScript adapter/compositor checks, TypeScript and Effect
checks, production package build, and 56 Rust native checks passed; seven explicit
hardware/private-fixture cases remain ignored. GStreamer and mpv disguised-HLS
checks passed. The root JavaScript dependency audit has zero known advisories
after updating the development runner. The current locked native graph requires
Rust 1.96; it was compiled with Rust 1.98. No registry release is claimed.

The main branch is preserved. This document records experimental source and local
evidence, not universal device, codec or platform qualification.

The repository transfer completed on 2026-10-14 with the same repository ID.
The complete branch/tag manifest matched before and after, and the main commit
remained `7a85ad46b5f1ece4ae7cc1e7afb928e3d2c4dad2`. `REPOSITORY.json`
records that checkpoint. The old organization URL redirects to this repository.
