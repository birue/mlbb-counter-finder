# MLBB Counter Finder

Static hero counter page for Mobile Legends: Bang Bang. Deploy from this repository with Vercel.

## Files to upload

- `index.html` — main page Vercel serves.
- `patch_override.json` — manually maintained patch notes and hero change markers. Keep this beside `index.html` at repository root.
- `mlbb_hero_photos/` — hero portrait images used by the page. Keep folder name and filenames unchanged.

Do not upload `mlbb_hero_photos.zip`; extracted image files are used by the page. `mlbb_counter_finder.html` is a duplicate copy and is not needed for deployment.

## Update patch notes

Edit `patch_override.json`, then commit the file. Use hero names exactly as shown in the app. Allowed `change` values:

- `buff` — displays green ↑.
- `nerf` — displays red ↓.
- `mixed` or `adjustment` — displays no arrow, but note appears in hero details.

Example:

```json
{
  "patch": "Patch version or date",
  "updated": "YYYY-MM-DD",
  "source": "https://source-url",
  "heroes": {
    "Gloo": {
      "change": "nerf",
      "note": "Short summary of change",
      "source": "https://source-url"
    }
  }
}
```

Keep `index.html` and `patch_override.json` at the same repository level. The page fetches the JSON from the same origin. Opening `index.html` directly as a `file://` URL may block JSON loading in Chrome; test via Vercel or a local web server instead.

## Data note

Patch notes currently reflect the linked article in `patch_override.json`; they are manually recorded, not auto-synced from Moonton. Existing hero counter recommendations are separate and have not been independently verified against current matchup statistics.
