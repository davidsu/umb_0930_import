# Base44 Dev Environment

## App
Minimal Vite + React app (no backend, no database, no external services). No credentials required.

## Run
```
docker compose -f docker-compose.base44.yml up -d
```
App is served on host port 3000 (maps to Vite dev server on 5173). Live reload is active; edits to `src/` appear in the preview without a rebuild.

## Quirks
- `electron-to-chromium@1.5.443` (the registry's current `latest`) has a missing tarball (HTTP 404) as of 2026-09-30. It's pinned to `1.5.442` via an npm `overrides` block in `package.json` to unblock `npm install`. Revisit/remove the override once the registry tarball is restored.
- `vite.config.js` sets `server.host: true` and `allowedHosts: true` so the preview's external hostname is accepted.
