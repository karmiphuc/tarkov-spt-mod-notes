# Pending pitFireTeam Restore - 2026-06-28

Status: restored and accepted after user raid validation, then disabled again on 2026-06-29 due to the recurring pitFireTeam courier `Trader not found` warning.

## Restored Components

Restored from:

- `E:\Tarkov-SPT\_disabled_by_codex\loading-map-61-20260628-110553`

Server mod:

- `pitFireTeam-ServerMod`

Client plugins and AI dependencies:

- `pitFireTeam\pitFireTeam.dll`
- `DrakiaXYZ-BigBrain.dll`
- `DrakiaXYZ-Waypoints\DrakiaXYZ-Waypoints.dll`
- `DrakiaXYZ-Waypoints\navmesh`

Restored BepInEx configs:

- `xyz.pit.fireteam.cfg`
- `xyz.drakia.waypoints.cfg`

## Current Notable Config

From `xyz.pit.fireteam.cfg`:

- `HealthMultiplier = 2`
- `PatrolRadius = 30`
- `FollowDistance = 12`
- `MaximumPickup = 1`
- `PitFireTeam = true`
- `BadGuy = false`
- `PmcArmbands = true`
- `LoadoutManagement = Simple`
- Follower debug/command hotkeys are unset.

## Backup Before Restore

- `E:\Tarkov-SPT\_mod_backups\pitfireteam-restore-20260628-185105`

This backup includes:

- `SPT\user\mods`
- `BepInEx\plugins`
- `BepInEx\config`
- `SPT\user\profiles`

## Verification

SPT server startup after restore:

- Cleaned up a duplicate server-process start and restarted with one `SPT.Server`.
- Loaded 16 server mods.
- Loaded `PitFireTeam version: 0.8.5`.
- Logged `PitFireTeam loaded`.
- Registered courier trader `67d3a28a3d6f4f7dbd09ed13`.
- Reached `Server has started, happy playing`.

Launcher:

- Connected to `https://127.0.0.1:6969`.
- Reported `SPT MatchingVersion: 4.0.13`.

Warning observed:

- `Trader: 67d3a28a3d6f4f7dbd09ed13 not found, generating temp entry with default refresh time of: 3600`
- This did not block startup, but profile state should be watched because this same trader ID previously needed cleanup when pitFireTeam was disabled.

Accepted:

- EFT client-side plugin load after pressing Play.
- Map load beyond 60-61%.
- User reported the later combined setup stable; this layer is now listed in `stable-state-2026-06-28.md`.

## Later Disable

On 2026-06-29, pitFireTeam was disabled again because SPT continued to log:

- `Trader: 67d3a28a3d6f4f7dbd09ed13 not found, generating temp entry with default refresh time of: 3600`

Profile cleanup alone did not stop the warning. The active pitFireTeam startup reintroduced the courier trader behavior, so the whole pitFireTeam group was moved to:

- `E:\Tarkov-SPT\_disabled_by_codex\trader-not-found-pitfireteam-20260629-051830`

See:

- `pending-pitfireteam-trader-cleanup-2026-06-29.md`

## Rollback

If restoring pitFireTeam again, restore or disable this group together:

- `SPT\user\mods\pitFireTeam-ServerMod`
- `BepInEx\plugins\pitFireTeam`
- `BepInEx\plugins\DrakiaXYZ-BigBrain.dll`
- `BepInEx\plugins\DrakiaXYZ-Waypoints`
- `BepInEx\config\xyz.pit.fireteam.cfg`
- `BepInEx\config\xyz.drakia.waypoints.cfg`

Then restore or compare against:

- `E:\Tarkov-SPT\_mod_backups\pitfireteam-restore-20260628-185105`
