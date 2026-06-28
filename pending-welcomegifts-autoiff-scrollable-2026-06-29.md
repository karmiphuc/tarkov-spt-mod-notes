# Pending WelcomeGifts / AutoIFF / ScrollableAttachments Layer - 2026-06-29

Status: reported stable so far and folded into the baseline. AutoIFF was adjusted afterward because it loaded but skipped PMC raids with its default activation mode.

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

- `BepInEx\plugins\ScrollableAttachments\ScrollableAttachments.dll`
- `BepInEx\plugins\zzzz-maschine-AutoIFF\maschine-AutoIFF.dll`

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

- Fresh EFT launch after moving AutoIFF into `zzzz-maschine-AutoIFF`.
- AutoIFF no longer logs `Skipping activation (mode=Automatic, side=Usec)`.

## AutoIFF Adjustment

Evidence from `BepInEx\LogOutput.log` before the fix:

- AutoIFF loaded before pitFireTeam.
- AutoIFF logged `Skipping activation (mode=Automatic, side=Usec)` in PMC raids.

Live changes:

- `BepInEx\config\com.maschine.AutoIFF.cfg`: changed `ActivationMode = Automatic` to `ActivationMode = AlwaysOn`.
- Moved `BepInEx\plugins\maschine-AutoIFF.dll` to `BepInEx\plugins\zzzz-maschine-AutoIFF\maschine-AutoIFF.dll`.

Backup before the AutoIFF change:

- `E:\Tarkov-SPT\_mod_backups\stable-autoiff-20260629-064610`

## Rollback

If this layer causes startup, menu, quest/mail, profile, or raid-load problems, disable these together:

- `SPT\user\mods\EFCL-WelcomeGifts`
- `BepInEx\plugins\zzzz-maschine-AutoIFF`
- `BepInEx\plugins\ScrollableAttachments`

WelcomeGifts can add gift quests/mail. If any gifts are claimed before rollback, check for profile references before removing the mod permanently.
