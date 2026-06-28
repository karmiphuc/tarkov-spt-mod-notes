# SPT Stable State - 2026-06-28

Validated by user:

- Base setup: played 3 raids for about 1 hour with no map-load hang or startup blocker.
- Added QoL/content batch below: user reported stable so far after install.
- Later item-info QoL, pitFireTeam restore, reduced WTT CommonLib/SNACC layer, and UnderFire tuning are accepted into the current stable baseline.

## Install Paths

- Steam EFT: `E:\Steam\steamapps\common\Escape from Tarkov`
- SPT install: `E:\Tarkov-SPT`
- Source mod archive folder: `D:\EFTarkov-mods`
- Original stable snapshot created: `2026-06-28 12:47:45 +08`
- Current accepted modlist updated: `2026-06-28`, after later validation layers.

## Active Server Mods

Location: `E:\Tarkov-SPT\SPT\user\mods`

- `[SVM] Server Value Modifier`
- `Infinite-Stash`
- `MergeConsumablesServer`
- `MoreCheckmarksBackend`
- `OldTarkovMovementServer`
- `Refringe-BetterBackpacks`
- `SNACC`
- `SkillsExtended`
- `TKMaida-PostRaidResources`
- `WTT-ServerCommonLib`
- `com.swiftxp.spt.showmethemoney`
- `mpstark-dynamicmaps`
- `net.skydust.sptarkovammocases`
- `ozen-Foldables`
- `ozen-InstantInsurance`
- `pitFireTeam-ServerMod`
- `traderJeronimo`
- `utjan.AirFilterOnlyDrainsInRaid`

## Active Client Plugins

Location: `E:\Tarkov-SPT\BepInEx\plugins`

- `AirFilterQOLClientMod.dll`
- `BetterBackpacks.dll`
- `DrakiaXYZ-BigBrain.dll`
- `DrakiaXYZ-Waypoints\DrakiaXYZ-Waypoints.dll`
- `DynamicMaps\DynamicMaps.dll`
- `IcyClawz.MunitionsExpert.dll`
- `KnifeSprint.dll`
- `MergeConsumables\MergeConsumables.dll`
- `MoreCheckmarks\MoreCheckmarks.dll`
- `OldTarkovMovement.dll`
- `PostRaidResources.dll`
- `ReduceFakeInteriorShadow.dll`
- `SkillsExtended\SkillsExtended.dll`
- `SkillsExtended\SkillsExtendedCommon.dll`
- `SmoothTalker\SmoothTalker.dll`
- `WTT-ClientCommonLib\WTT-ClientCommonLib.dll`
- `WTT-ClientCommonLib\WTT-ClientCommonLibFika.dll`
- `com.swiftxp.spt.showmethemoney\SwiftXP.SPT.ShowMeTheMoney.Client.dll`
- `infinitestash.dll`
- `ozen-Foldables\Foldables.dll`
- `pitFireTeam\pitFireTeam.dll`
- `rpmwpm.UnderFire.dll`
- SPT core plugins under `spt\`

## Active BepInEx Patchers

Location: `E:\Tarkov-SPT\BepInEx\patchers`

- `SkillsExtended_PrePatch.dll`
- SPT core patcher `spt-prepatch.dll`

## Stability Tweaks

- `OldTarkovMovementServer\Config\settings.jsonc`: `BotsUseOldMovement` is `false`.
- `SkillsExtended\Resources\Configs\ServerConfig.json`: update check is disabled.
- `com.rpmwpm.UnderFire.cfg`: adrenaline still triggers from suppression, but tunnel vision and tremor are disabled.
- Reduced WTT layer is accepted as `WTT-ServerCommonLib`, `WTT-ClientCommonLib`, and `SNACC` only.
- New-mod rollback backup from this batch: `E:\Tarkov-SPT\_mod_backups\newmods-20260628-135126`

## Disabled For Stability

Location: `E:\Tarkov-SPT\_disabled_by_codex`

These folders are rollback/staging leftovers and should not be treated as the live active state. Current active state is listed above.

- `loading-map-61-20260628-110553`
  - old disabled copies of `pitFireTeam-ServerMod`, `pitFireTeam`, `DrakiaXYZ-BigBrain.dll`, and `DrakiaXYZ-Waypoints`; this group was later restored and accepted.
- `startup-missing-bigbrain-20260628-111451`
  - disabled `WeekendDrops`
  - disabled `WeekendDropsUI`
  - disabled `com.20fpsguy.WeekendDrops.cfg`
- `remove-caliber-clearprepare-20260628-112108`
  - disabled `CaliberUnderName.dll`
  - disabled `ClearPrepareScreen.dll`
  - disabled `com.slpf.caliberundername.cfg`
- `remove-handy-restore-20260628-215600`
  - disabled `Handy`
  - disabled `RestoreTheOldNumberOfMedicalUses`

## Profile Cleanup Done

- Removed stale `pitFireTeam` trader reference `67d3a28a3d6f4f7dbd09ed13` from the PMC profile.
- Profile backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\remove-pitfireteam-trader-20260628-112108`
- Earlier orphan item cleanup backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\codex-orphan-cleanup-20260628-110653`

## Notes

- Keep `DynamicMaps` enabled in this stable baseline; it loaded and worked during the successful test.
- The added QoL/content batch includes inventory/tooling mods plus `traderJeronimo`; if a future profile issue appears, check trader/profile references before broad disabling.
- `pitFireTeam`, `BigBrain`, and `Waypoints` are now part of the accepted active baseline. If they break later, disable them as a group and compare against the `pitfireteam-restore-20260628-185105` backup.
- Do not re-enable `WeekendDrops`, `CaliberUnderName`, `ClearPrepareScreen`, `Handy`, or `RestoreTheOldNumberOfMedicalUses` without testing one at a time.
- If the 60-61% loading-map hang returns, compare against this file first.
