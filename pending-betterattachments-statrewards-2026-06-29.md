# Pending BetterAttachments / StatRewards Layer - 2026-06-29

Status: installed and server-start validated. Not yet accepted into the stable baseline until at least one normal raid is tested.

## Installed Archives

Source archives from `D:\`:

- `DeadW0lf-BetterAttachment_v406.1.0.0.zip`
  - SHA256: `a5e7ec95a33c5feb52fbb123fafddb37d903f757f4f8fc480765fcf35f45ec3a`
- `StatRewards-1.1.1.zip`
  - SHA256: `57710a0cb2204eb4961b89e712bae91c522ff0f69c8f9a5ae853c6af1ae094fd`

## Installed Components

Server mods added:

- `SPT\user\mods\BetterAttachments`
- `SPT\user\mods\StatRewards`

No BepInEx client plugins or patchers were added by these archives.

## BetterAttachments Ergonomics Tune

Edited file:

- `E:\Tarkov-SPT\SPT\user\mods\BetterAttachments\config\config.json`

The downloaded config had large ergonomics buffs, often around 40-50%. The live config was mass-tuned down before installation:

- Only entries already improved by BetterAttachments were changed.
- Entries with no existing ergonomics buff were left unchanged.
- Positive ergonomics buffs target about +10%, rounded to a whole number and never increased above the downloaded config value.
- Negative ergonomics penalties target about 10% relief toward zero.
- Recoil, heating, and feature toggles were left untouched.

Tune stats:

- Total attachment entries: 1092
- Existing positive ergonomics buffs: 246
- Existing negative penalty relief entries: 236
- Values changed by tune: 325
- Values left unchanged: 767
- Post-tune positive buff ratio min / median / max: `1.071 / 1.100 / 1.200`
- Post-tune negative penalty relief min / median / max: `0.100 / 1.000 / 1.000`

The high relief on some negative penalties is from tiny whole-number values such as `-1 -> 0`; there is no smaller integer buff available while keeping the item improved.

Example positive changes:

- `TangoDown Stubby BGV-MK46K foregrip (Black)`: `9 -> 13` tuned to `10`
- `Magpul M-LOK AFG tactical foregrip (Black)`: `11 -> 15` tuned to `12`
- `Magpul AFG tactical foregrip (Black)`: `10 -> 14` tuned to `11`
- `Fortis Shift tactical foregrip`: `12 -> 16` tuned to `13`

Example negative change:

- `Zenit RK-2 tactical foregrip`: `-4 -> -2` tuned to `-3`

## Backup Before Install

- `E:\Tarkov-SPT\_mod_backups\install-betterattachments-statrewards-20260629-184603`

This backup includes:

- `SPT\user\mods`
- `SPT\user\profiles`
- `BepInEx\plugins`
- `BepInEx\config`
- Source archives
- Server/client manifests before and after install
- `BetterAttachments-config-original.json`
- `BetterAttachments-config-tuned.json`
- `BetterAttachments-ergo-tune.txt`

## Verification

SPT server startup after install:

- Started `E:\Tarkov-SPT\SPT\SPT.Server.exe` for validation.
- Loaded 22 server mods.
- Loaded `BetterAttachments version: 1.0.0`.
- Loaded `StatRewards version: 1.1.1`.
- `StatRewards` loaded 48 milestone definitions and created its `progress` directory.
- `BetterAttachments` updated 1092 attachments.
- Reached `Server has started, happy playing`.
- Validation server process was stopped afterward.

Known warning still present:

- Existing pitFireTeam courier warning remains: `Trader: 67d3a28a3d6f4f7dbd09ed13 not found`.
- This warning was already accepted while pitFireTeam remains a must-have and did not block startup.

## Not Yet Verified

- EFT reaches main menu with this layer active.
- One full raid loads without the 60-61% loading-map hang.
- BetterAttachments values feel mild enough in-game.
- StatRewards post-raid reward checks behave correctly after a milestone is reached.

## Rollback

If startup, menu, stash, profile, item, or raid-load problems appear, disable these folders together:

- `E:\Tarkov-SPT\SPT\user\mods\BetterAttachments`
- `E:\Tarkov-SPT\SPT\user\mods\StatRewards`

`StatRewards` creates local progress data under its own mod folder after server start. If removing the mod, keep or delete that progress folder together with the mod folder depending on whether the mod will be retested later.

BetterAttachments does not add new item IDs; it patches attachment stats from config at startup. Disabling it should not require profile cleanup.
