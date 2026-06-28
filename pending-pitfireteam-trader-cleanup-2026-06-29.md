# Pending pitFireTeam Trader Cleanup - 2026-06-29

Status: pitFireTeam group restored again because it is must-have. The recurring courier `Trader not found` warning is accepted as non-fatal while pitFireTeam remains active.

## Symptom

SPT server startup repeatedly logged:

- `Trader: 67d3a28a3d6f4f7dbd09ed13 not found, generating temp entry with default refresh time of: 3600`

The same run also logged:

- `Registered courier trader '67d3a28a3d6f4f7dbd09ed13'`

This identifies the trader ID as pitFireTeam's courier trader.

## Profile Cleanup

Profile backup before cleanup:

- `E:\Tarkov-SPT\_mod_backups\profile-cleanup\trader-not-found-pitfireteam-20260629-051724`

Removed from the active profile:

- `characters.pmc.TradersInfo.67d3a28a3d6f4f7dbd09ed13`
- `dialogues.67d3a28a3d6f4f7dbd09ed13`

After cleanup:

- Profile JSON valid.
- `TradersInfo` no longer had the courier trader ID.
- `dialogues` no longer had the courier trader ID.
- Orphan inventory references: 0.
- Missing insured-item references: 0.

The warning still returned while pitFireTeam remained active, so the source was active pitFireTeam startup behavior rather than only stale profile data.

## Temporary Disable

Disabled location:

- `E:\Tarkov-SPT\_disabled_by_codex\trader-not-found-pitfireteam-20260629-051830`

Moved out of the active install:

- `SPT\user\mods\pitFireTeam-ServerMod`
- `BepInEx\plugins\pitFireTeam`
- `BepInEx\plugins\DrakiaXYZ-BigBrain.dll`
- `BepInEx\plugins\DrakiaXYZ-Waypoints`

## Must-Have Restore

Restored from:

- `E:\Tarkov-SPT\_disabled_by_codex\trader-not-found-pitfireteam-20260629-051830`

Backup before restoring:

- `E:\Tarkov-SPT\_mod_backups\restore-pitfireteam-musthave-20260629-052119`

Restored components:

- `SPT\user\mods\pitFireTeam-ServerMod`
- `BepInEx\plugins\pitFireTeam`
- `BepInEx\plugins\DrakiaXYZ-BigBrain.dll`
- `BepInEx\plugins\DrakiaXYZ-Waypoints`

Latest startup after restore:

- Loaded `PitFireTeam version: 0.8.5`.
- Logged `Registered courier trader '67d3a28a3d6f4f7dbd09ed13'`.
- Logged `PitFireTeam loaded`.
- Reached `Server has started, happy playing`.
- The courier `Trader not found` warning returned and is accepted for this setup.

## Verification

SPT server startup after temporarily disabling pitFireTeam:

- Loaded 19 server mods.
- Did not load `PitFireTeam`.
- Did not register courier trader `67d3a28a3d6f4f7dbd09ed13`.
- No `Trader:` warning appeared in the fresh startup block.
- Reached `Server has started, happy playing`.

Profile check after restart:

- `TradersInfo` does not contain `67d3a28a3d6f4f7dbd09ed13`.
- `dialogues` does not contain `67d3a28a3d6f4f7dbd09ed13`.
- Orphan inventory references: 0.
- Missing insured-item references: 0.

Profile check immediately after restoring pitFireTeam again:

- `TradersInfo` still does not contain `67d3a28a3d6f4f7dbd09ed13`.
- `dialogues` still does not contain `67d3a28a3d6f4f7dbd09ed13`.
- Orphan inventory references: 0.
- Missing insured-item references: 0.

Profile check after later stable play:

- `TradersInfo` contains `67d3a28a3d6f4f7dbd09ed13` again.
- `dialogues` does not contain `67d3a28a3d6f4f7dbd09ed13`.
- Orphan inventory references: 0.
- Missing insured-item references: 0.
- Treat the `TradersInfo` entry as part of active pitFireTeam state; clean it only if pitFireTeam is disabled again.

## Current Tradeoff

pitFireTeam is worth keeping for AI teammate functionality. Do not disable it again just for the courier warning; only revisit if it causes a real main-menu, profile, or raid blocker. If it is disabled, clean courier ID `67d3a28a3d6f4f7dbd09ed13` from `TradersInfo` and `dialogues`.
