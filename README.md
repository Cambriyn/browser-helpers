# Browser helper programs, built

Two small helper programs for driving a browser, built from fixed upstream commits for macOS on Apple silicon (arm64). This repository holds only the built files (as release assets), their checksums and these build notes. It holds no other source.

## Files (release `2026-11-17`)

| File | Upstream | Commit | Build command | SHA-256 | Bytes |
|---|---|---|---|---|---|
| `agent-browser-6b7367b0c1a93c4a510835973ba856777ca77a91-darwin-arm64` | `vercel-labs/agent-browser`, branch `laf/bidi-attach` (upstream pull request 2227: attach to a running Firefox over WebDriver BiDi) | `6b7367b0c1a93c4a510835973ba856777ca77a91` | `cargo build --release --locked` with build paths remapped (`--remap-path-prefix`), in `cli/` (the dashboard is not built: the binary embeds upstream's placeholder page) | `032e925fc08a5f257e3d76be135e21cd532f1acaa2ecde3e8e977f63b38ef0bb` | 17063872 |
| `camoufox-cli-933ae2e8ba7a00e254b4d4075eb0e85a527289fc-darwin-arm64` | `Pedrvisk/camoufox-rust`, crate `camoufox-cli` (binary `camoufox`) | `933ae2e8ba7a00e254b4d4075eb0e85a527289fc` | `cargo build --release --locked -p camoufox-cli` with build paths remapped | `d98179547a22b4e62e3b9e45165c3bd7be125e268fa739bf7d2c11d8945ac60a` | 9731936 |

Toolchain: rustc 1.99.1 (58cf8f9c3 2026-10-13), cargo 1.99.1, Apple clang 21.0.0, macOS 26.4.1 on arm64.

## Checking a download

```bash
shasum -a 256 -c SHA256SUMS
```

## Not here

The Camoufox browser itself is taken from its own upstream release (`daijro/camoufox`), checked against the SHA-256 upstream publishes.

Each program keeps its upstream license; see the upstream repositories named above.
