# Pitch Releases

Signed and notarized release artifacts for [Pitch](https://github.com/mmorper/pitch) — a desktop app for presenting URL-based content (HTML, Markdown, PDF, images, SVG, Google Slides, remote URLs) as ordered "pitches."

## Why a separate repo?

The Pitch source repo is private. This public repo exists so that:

1. **GitHub Releases can host `.dmg` downloads** that anyone can grab without a GitHub account or auth token.
2. **`electron-updater` can read the auto-update feed** (`latest-mac.yml` + signed DMGs) from a public endpoint. Embedding a `GH_TOKEN` in the released app to read from a private repo would be a security non-starter — any installed user could extract the token.

Build pipeline:

```
mmorper/pitch (private)  →  electron-builder  →  this repo's Releases
       ↓ source                 ↑
       └─ npm run package:mac ──┘
```

## Releases

The [Releases page](https://github.com/mmorper/pitch-releases/releases) lists every published version. Each release attaches:

- `Pitch-<version>-arm64.dmg` — Apple Silicon
- `Pitch-<version>.dmg` — Intel
- `latest-mac.yml` — the auto-update feed manifest (produced automatically by electron-builder)

All `.dmg` files are signed with `Developer ID Application` and notarized by Apple — double-click to open, no Gatekeeper warning.

## Installing Pitch

1. Download the `.dmg` for your Mac architecture from the latest [Release](https://github.com/mmorper/pitch-releases/releases/latest).
2. Open the DMG and drag Pitch to Applications.
3. Open Pitch from Applications.

Once installed, Pitch updates itself automatically — new releases are picked up on app launch and applied on next restart.

## Issues and source

- **Issues, discussions, and roadmap:** [`mmorper/pitch`](https://github.com/mmorper/pitch) (source repo — request access if needed).
- **License + contributor info:** lives in the source repo.

## Not affiliated with

[Pitch.com](https://pitch.com) (the SaaS slide-deck product). Different project, different team, no relationship — name collision only.
