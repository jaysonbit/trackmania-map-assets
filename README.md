# trackmania-map-assets

Hosting for custom assets (sign images, videos, sounds, mods) used in our
Trackmania maps. Maps are built at home and played at the office via our club,
so every asset needs a public, stable URL - this repo provides that through
GitHub raw links.

## Structure

```
shared/                 Assets reused across many maps
  signs/                Logos, office/club branding, generic sign images
  videos/               .webm clips for screens/signs
  sounds/               .ogg music and sound effects
  mods/                 Texture mod .zip packs
maps/
  _template/            Copy this when starting a new map
  <map-name>/           One folder per map
    README.md           Which asset goes where + its URL
    signs/
    videos/
    sounds/
    mod/
```

## Getting a URL

```
https://raw.githubusercontent.com/jaysonbit/trackmania-map-assets/main/<path>
```

Example: `shared/signs/club-logo-v1.png` ->
`https://raw.githubusercontent.com/jaysonbit/trackmania-map-assets/main/shared/signs/club-logo-v1.png`

The repo must be **public** for these links to work in-game.

## Conventions

- **Lowercase, hyphens, no spaces** in file and folder names (`office-lobby-v1.png`, not `Office Lobby.png`) - spaces and special characters break URLs.
- **Version in the filename** (`-v1`, `-v2`, ...). Trackmania caches downloaded assets by URL, so overwriting a file at the same path often won't show up in-game. Add a new version, update the URL in the map, and leave the old file until no map uses it.
- **Don't delete or rename** files a published map points to - the map will lose the asset.
- **No Git LFS.** Raw links to LFS files return a pointer file, not the asset.
- Keep files game-ready and small; working files (`.psd`, `.blend`, ...) are git-ignored.
- Record every URL you use in the map's `README.md` so it's easy to find what's live.

## New map

1. Copy `maps/_template` to `maps/<map-name>`.
2. Drop assets into the matching subfolder.
3. Commit and push, then paste the raw URL into the editor.
