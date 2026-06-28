# Pending WTT CommonLib Group - 2026-06-28

Status: reduced after client main-menu/profile load failure. `WTT-CommonLib` and `SNACC` remain active; `Handy` and `RestoreTheOldNumberOfMedicalUses` are disabled.

## Installed Archives

Copied source archives into `D:\EFTarkov-mods`:

- `WTT-CommonLib-v2.0.20.zip`
  - SHA256: `c37bb8ee5205432d41cfc3c22c1ec4c3fe509a94b69293c5433ff5e9bcc9974a`
- `RestoreTheOldNumberOfMedicalUses-1.0.0.zip`
  - SHA256: `068abf2aaf9311a506d5c6bfc1fcc7cd221715a93fc69f819b752f54672c73c4`
- `SNACC.zip`
  - SHA256: `52857c4df9d98f9eeebc96172ddc7f6c5113612a4456cb02b8b799595123f7c5`
- `Handy.zip`
  - SHA256: `b963fbb20f947f8b8fea0907b6eceadbb8d66dee27e21d29417bbb8676c1a07c`

## Install Order

Originally installed in this order:

1. `WTT-CommonLib-v2.0.20`
2. `RestoreTheOldNumberOfMedicalUses-1.0.0`
3. `SNACC`
4. `Handy`

`SNACC` and `Handy` reference `WTT-ServerCommonLib` in their dependency metadata. SPT's mod validator prints metadata in its own order and still lists `WTT-ServerCommonLib` near the end, but the server resolves the dependency and reaches ready state.

## Active Components

Server mods added:

- `WTT-ServerCommonLib` - WTT CommonLib `2.0.20`
- `RestoreTheOldNumberOfMedicalUses` - `1.0.0`
- `SNACC` - SnaccPack `1.0.0`
- `Handy` - Handy Toolbox `1.0.0`

Client plugin added:

- `WTT-ClientCommonLib\WTT-ClientCommonLib.dll`
- `WTT-ClientCommonLib\WTT-ClientCommonLibFika.dll`

## Reduction After Failure

The game failed to load cleanly to main menu after the full 4-mod group was installed. The reduced active set is:

- Keep `WTT-ServerCommonLib`
- Keep `WTT-ClientCommonLib`
- Keep `SNACC`
- Disable `Handy`
- Disable `RestoreTheOldNumberOfMedicalUses`

Disabled files moved to:

- `E:\Tarkov-SPT\_disabled_by_codex\remove-handy-restore-20260628-215600`

Backup before this reduction:

- `E:\Tarkov-SPT\_mod_backups\remove-handy-restore-20260628-215529`

Profile cleanup after reduction:

- Removed 13 orphan inventory items whose mail/insurance parent stashes no longer existed.
- Removed 13 matching `InsuredItems` references.
- Removed `Handy Toolbox` and `RestoreTheOldNumberOfMedicalUses` from the profile's `spt.mods` metadata list.
- Dedicated profile backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\orphan-items-after-handy-20260628-220044`
- Post-cleanup validation: profile JSON is valid, PMC inventory has 0 orphan parent references, and `InsuredItems` has 0 references to missing items.

## Backup Before Install

- `E:\Tarkov-SPT\_mod_backups\commonlib-group-20260628-212925`

This backup includes:

- `SPT\user\mods`
- `BepInEx\plugins`
- `BepInEx\config`
- `SPT\user\profiles`

## Verification

SPT server startup for original 4-mod group:

- Cleaned up duplicate server processes and restarted with one `SPT.Server`.
- Loaded 20 server mods.
- Loaded `WTT-ServerCommonLib version: 2.0.20`.
- Loaded `RestoreTheOldNumberOfMedicalUses version: 1.0.0`.
- Loaded `SnaccPack version: 1.0.0`.
- Loaded `Handy Toolbox version: 1.0.0`.
- `RestoreTheOldNumberOfMedicalUses` logged `The mod is loaded.`
- Reached `Server has started, happy playing`.

Launcher:

- Connected to `https://127.0.0.1:6969`.
- Reported `SPT MatchingVersion: 4.0.13`.

Warning still present:

- `Trader: 67d3a28a3d6f4f7dbd09ed13 not found, generating temp entry with default refresh time of: 3600`
- This warning is from the pending pitFireTeam layer, not from the WTT CommonLib group.

Not yet verified:

- EFT client-side plugin load after pressing Play.
- One full raid without map-load hang or item/profile errors.

## Verification After Reduction

SPT server startup after disabling `Handy` and `RestoreTheOldNumberOfMedicalUses`:

- Loaded 18 server mods.
- Loaded `SnaccPack version: 1.0.0`.
- Loaded `WTT-ServerCommonLib version: 2.0.20`.
- Did not load `Handy Toolbox`.
- Did not load `RestoreTheOldNumberOfMedicalUses`.
- Reached `Server has started, happy playing`.

Launcher after profile cleanup:

- Connected to `https://127.0.0.1:6969`.
- Reported `SPT MatchingVersion: 4.0.13`.

Still pending:

- Press Play again and confirm the main menu loads without item deserialization errors.
- Run one short raid before promoting this reduced set.

## Rollback

If this group causes startup, item, or profile problems, disable/remove together:

- `SPT\user\mods\WTT-ServerCommonLib`
- `SPT\user\mods\RestoreTheOldNumberOfMedicalUses`
- `SPT\user\mods\SNACC`
- `SPT\user\mods\Handy`
- `BepInEx\plugins\WTT-ClientCommonLib`

Then restore or compare against:

- `E:\Tarkov-SPT\_mod_backups\commonlib-group-20260628-212925`
