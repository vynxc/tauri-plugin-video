# Tauri video plugin

Standalone native video playback for Tauri, maintained at
`vynxc/tauri-plugin-video`. The Rust crate is `tauri-plugin-video`; its JavaScript
adapter is `@vynxc/video-tauri`. The platform-neutral `@get-air/video` peer remains
independently maintained. This repository was imported from
`get-air/tauri-video-plugin` at `6baf19ff74bfe5278838f05d9eaa4af55ecc4d05`;
upstream licenses and Git history are preserved.

The host owns its layout, controls, navigation and media selection. The plugin
adapts selected media to native engines and publishes typed playback facts and
commands. No application account, metadata provider, tracking integration or
product-specific UI is required.

Linux supports GStreamer by default and explicit mpv. Windows has its existing
native GStreamer surface. Android uses Media3 by default with explicit LibVLC.
Engine availability, codecs, HDR, DRM and live/DVR behavior are reported runtime
facts rather than platform-wide guarantees. The existing unsupported-host errors
remain for hosts without an implemented native surface.

The plugin includes session-owned source replacement, validated request headers,
independent audio/subtitle track controls, live timeline facts, native picture
presentation and ordered shutdown. Its desktop loopback HLS proxy sanitizes
supported disguised segments while retaining the source's validated authorization.

Package and crate are version `0.4.0`, using native IPC protocol `1`. The declared
`@get-air/video` peer range is `>=0.3.0 <0.4.0`. The generic identity and namespace
changes live on the experimental branch; no release or main-branch change is
claimed. Historical product-specific documentation remains in Git history.

[Protocol and runtime architecture](SPEC.md) ·
[Platform documentation](docs/) · [Compatibility](VERSIONING.md)

The locked native dependency graph requires Rust 1.96 or newer. JavaScript
development checks use Node.js 22.12 or newer. The root JavaScript dependency
audit reports no known vulnerabilities.

License: MIT OR Apache-2.0.
