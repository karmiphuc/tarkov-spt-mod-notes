# Pending pitFireTeam Trader Cleanup - 2026-06-29

Status: pitFireTeam group disabled after recurring `Trader not found` warning.

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

## Disabled Components

Disabled location:

- `E:\Tarkov-SPT\_disabled_by_codex\trader-not-found-pitfireteam-20260629-051830`

Moved out of the active install:

- `SPT\user\mods\pitFireTeam-ServerMod`
- `BepInEx\plugins\pitFireTeam`
- `BepInEx\plugins\DrakiaXYZ-BigBrain.dll`
- `BepInEx\plugins\DrakiaXYZ-Waypoints`

## Verification

SPT server startup after disabling pitFireTeam:

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

## Current Tradeoff

Keeping pitFireTeam disabled removes the warning and keeps the profile clean, but removes AI teammate functionality. Re-enable the group only if that feature is worth accepting or debugging the courier-trader warning again.
