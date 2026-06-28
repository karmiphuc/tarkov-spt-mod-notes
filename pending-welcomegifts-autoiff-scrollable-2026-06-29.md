# Pending WelcomeGifts / AutoIFF / ScrollableAttachments Layer - 2026-06-29

Status: installed and server-start verified, but not accepted into the stable baseline yet.

## Installed Archives

Source archives moved into `D:\EFTarkov-mods`:

- `mod_EFCL-WelcomeGifts-v400.7z`
  - SHA256: `1f46f4773582da027fa4532d0b085a8f962cbcda88baa3dabeac0d3161260071`
- `maschine-AutoIFF-1.0.0.zip`
  - SHA256: `ca69e3a85035c60e9e1a723605ba8b7d3e327561794888e257537655508451ac`
- `ScrollableAttachments.7z`
  - SHA256: `29dc3019f369b0ca3a2b0564ab0a9337d847025dd0149d43bef22a857f5786b2`

## Installed Components

Server mod added:

- `SPT\user\mods\EFCL-WelcomeGifts`

Client plugins added:

- `BepInEx\plugins\maschine-AutoIFF.dll`
- `BepInEx\plugins\ScrollableAttachments\ScrollableAttachments.dll`

Dependency already present:

- `WTT-ServerCommonLib`

## Backup Before Install

- `E:\Tarkov-SPT\_mod_backups\install-welcomegifts-autoiff-scrollable-20260629-050944`

This backup includes:

- `SPT\user\mods`
- `BepInEx\plugins`
- `BepInEx\config`
- `SPT\user\profiles`

## Verification

SPT server startup after install:

- Loaded 21 server mods.
- Loaded `Welcome Gifts version: 4.0.0`.
- Loaded existing `WTT-ServerCommonLib version: 2.0.20`.
- Reached `Server has started, happy playing`.
- Port `127.0.0.1:6969` was listening from `SPT.Server`.

Profile check after server startup:

- Profile JSON valid.
- Inventory item count: 868.
- Orphan inventory references: 0.
- Missing insured-item references: 0.

Warnings still present:

- Existing pitFireTeam trader warning: `Trader: 67d3a28a3d6f4f7dbd09ed13 not found`.

Follow-up note:

- PackNStrap was later disabled due to item-base warnings.
- After disabling PackNStrap, the WelcomeGifts layer still loaded with SPT reaching `Server has started, happy playing`.

Not yet verified:

- EFT reaches main menu with `maschine-AutoIFF.dll` and `ScrollableAttachments.dll` loaded.
- WelcomeGifts quests/mail/gift UI behaves correctly.
- One raid loads without a 60-61% map-load hang.

## Rollback

If this layer causes startup, menu, quest/mail, profile, or raid-load problems, disable these together:

- `SPT\user\mods\EFCL-WelcomeGifts`
- `BepInEx\plugins\maschine-AutoIFF.dll`
- `BepInEx\plugins\ScrollableAttachments`

WelcomeGifts can add gift quests/mail. If any gifts are claimed before rollback, check for profile references before removing the mod permanently.
