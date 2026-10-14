# Compatibility

The standalone JavaScript adapter is `@vynxc/video-tauri` and the Rust crate is
`tauri-plugin-video`. Both are currently version `0.4.0`, with native IPC protocol
`1` and a declared `@get-air/video` peer range of `>=0.3.0 <0.4.0`.

The platform-neutral peer has an independent version. Native diagnostics report
the actual crate/protocol pair; incompatible command and error schemas fail the
adapter handshake. Additive diagnostics and capability facts remain represented
by the current protocol. No registry publication is claimed for this experimental
standalone namespace.
