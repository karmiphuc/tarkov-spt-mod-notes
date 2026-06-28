# Pending PackNStrap / DPX / UseItemsAnywhere Layer - 2026-06-29

Status: installed and server-start verified, but not accepted into the stable baseline yet.

## Installed Archives

Source archives from `D:\`:

- `DPX-ElectronicsCase-v1.1.0-SPT-4.0.13.zip`
  - SHA256: `b3a43513f15b39e80671a61b7c89dcb15fb4ab75b6b32c870f6f9ece9cb7817e`
- `WTT-PackNStrap-2.0.4.7z`
  - SHA256: `48b7e5c1c719aa7f0f83917e1c1189de5062d9c73968250ecb37e8ece466bcde`
- `UseItemsAnywhere-Release-1.3.2-06f9fa88.zip`
  - SHA256: `f4ed99a4d67f4460e3ebd5da87dae36fde26a7c020a024fb3d263269788b059b`

## Installed Components

Server mods added:

- `SPT\user\mods\DPX-ElectronicsCase`
- `SPT\user\mods\WTT-PackNStrap`

Client plugins added:

- `BepInEx\plugins\UseItemsFromAnywhere.dll`
- `BepInEx\plugins\WTT-PackNStrap\Trenchfoot-BeltSlot.dll`
- `BepInEx\plugins\WTT-PackNStrap\WTT-PackNStrap.dll`

Dependency already present:

- `WTT-ServerCommonLib`
- `WTT-ClientCommonLib`

## Backup Before Install

- `E:\Tarkov-SPT\_mod_backups\install-packnstrap-dpx-useitems-20260629-050411`

This backup includes:

- `SPT\user\mods`
- `BepInEx\plugins`
- `BepInEx\config`
- `SPT\user\profiles`

## Verification

SPT server startup after install:

- Loaded 20 server mods.
- Loaded `DPX Electronics Case version: 1.1.0`.
- Loaded `WTT-PackNStrapServer version: 2.0.4`.
- Loaded `WTT-ServerCommonLib version: 2.0.20`.
- Reached `Server has started, happy playing`.
- Port `127.0.0.1:6969` was listening from `SPT.Server`.

Warnings seen:

- Existing pitFireTeam trader warning remains: `Trader: 67d3a28a3d6f4f7dbd09ed13 not found`.
- PackNStrap introduced four `ItemBaseClassService` warnings for its own custom parent/category IDs:
  - `680fce2ec7b9b222270f074c`
  - `680fd1dae5044e670a092e16`
  - `68154651f849fb4e7d816738`
  - `6815465859b8c6ff13f94026`

Not yet verified:

- EFT reaches main menu with the new BepInEx plugins.
- One raid loads without a 60-61% map-load hang.
- New cases/belts render and behave correctly in stash/in raid.

## Rollback

If this layer causes startup, menu, profile, stash, item, or raid-load problems, disable these together:

- `SPT\user\mods\DPX-ElectronicsCase`
- `SPT\user\mods\WTT-PackNStrap`
- `BepInEx\plugins\UseItemsFromAnywhere.dll`
- `BepInEx\plugins\WTT-PackNStrap`

Before disabling after acquiring any custom PackNStrap or DPX items, remove those items from the profile/stash when possible. If profile errors appear after removal, compare against the backup above and check for orphan inventory or insured-item references.
