# GameBridge

A local-first Windows desktop companion for browsing a user's Steam library and comparing it with Discord's publicly documented game/activity capabilities.

## Project goals

- Read Steam library metadata without downloading or installing games.
- Show owned games, AppIDs, names, playtime (when available), and local install status.
- Maintain a local cache and searchable library.
- Compare Steam titles against a locally maintained, clearly sourced catalog of Discord-detectable games where licensing and source availability permit.
- Explain the difference between Discord Rich Presence, detected desktop game activity, and Discord profile-badge progress.

## Non-goals

- No game downloads or installation.
- No Steam or Discord password collection.
- No extraction, storage, or transmission of Discord session cookies, tokens, or authorization headers.
- No injection into Discord, internal store mutation, private API calls, fabricated game processes, or synthetic telemetry.
- No claim that Rich Presence or a visible status advances a Discord badge.

## Initial technical direction

- Python 3.12+
- PySide6 desktop UI
- SQLite local cache
- httpx for documented Steam Web API requests
- pytest for tests
- PyInstaller for Windows packaging (later milestone)

Keep network access explicit and minimal. Store user settings locally. Never commit API keys, tokens, cookies, .env files, or personal data.

## Milestones

1. Repository and development setup.
2. Steam library metadata importer (read-only; no installation).
3. Search, filters, install-state display, and local cache.
4. Discord capability/reference catalog using public documentation only.
5. UI polish and Windows packaging.

## Status

Initial planning. No Discord badge automation is implemented.
