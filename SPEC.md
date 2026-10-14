# Native video protocol and runtime

The plugin is a standalone Tauri adapter. Native engines render video while the
host web UI renders its own controls. `@get-air/video` supplies the typed client
contract; the plugin has no product metadata, account or backend API integration.

## IPC and ownership

Commands use the existing `plugin:video|` namespace and protocol version `1`.
Diagnostics identify the Rust crate, version, available engines and source-proxy
support before stateful attachment. The JavaScript package exposes the native
surface adapter and Effect integration. A successful protocol check is cached;
failed checks remain retryable.

A selected source opens under a session identity. Replacement retires the prior
engine and its private source state. Late close, callbacks and stale session
commands cannot retire a newer owner. Host shutdown stops engines on their
owning UI thread and releases process-owned proxy routes.

## Platforms

Linux's GStreamer transitions, seeks, track selection and timing queries run in
an ordered worker. GTK owns native widget allocation and presentation. Snapshots
contain completed telemetry. Volume uses a dedicated audio filter. Explicit mpv
redraws use the owning GL context and atomic update notification.

Windows retains its implemented native GStreamer surface. Android's default
Media3 engine presents through SurfaceView beneath the host WebView. LibVLC is
an explicit Android engine; media errors do not silently select another engine.
Other hosts retain their typed unavailable-surface result.

## Media and source authority

Sources carry a selected URI and bounded, validated headers. The plugin has no
provider search or stream-ranking policy. Its loopback desktop HLS proxy retains
validated source authorization, rewrites playlist media references to its own
routes and strips supported misleading segment prefixes. Source replacement and
shutdown release those routes. Public telemetry contains playback facts rather
than private source credentials.

Tracks retain audio/subtitle identity and supported selection. Source-native
live/DVR facts are separate from VOD duration and seek bounds. Native picture
modes preserve aspect ratio in their implemented viewport. Codec, HDR, DRM and
platform support depend on the actual engine/device evidence.

## Errors and diagnostics

Typed failures distinguish decoder/format, video/audio output, protected media,
source loading, runtime setup, authorization and network failures. Runtime error
domains/numeric codes establish their classification. Bounded, redacted source
refusal diagnostics do not replace the underlying engine error.

The implementation contains opt-in qualification fixtures for native playback,
seek, track controls, picture presentation, source refusal/recovery and shutdown.
These fixtures are separate from a universal device or format guarantee. Generic
qualification settings use the `TAURI_VIDEO_` prefix.
