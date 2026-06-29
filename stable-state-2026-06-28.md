# SPT Stable State - 2026-06-28

Validated by user:

- Base setup: played 3 raids for about 1 hour with no map-load hang or startup blocker.
- Added QoL/content batch below: user reported stable so far after install.
- Later item-info QoL, reduced WTT CommonLib/SNACC layer, and UnderFire tuning are accepted into the current stable baseline.
- pitFireTeam was restored and is treated as a must-have. Its courier trader startup warning is accepted as non-fatal while pitFireTeam stays active.
- WelcomeGifts, AutoIFF, and ScrollableAttachments were reported stable so far on 2026-06-29. AutoIFF was adjusted afterward because it was loading but skipping PMC raids.
- BetterAttachments and StatRewards were accepted on 2026-06-29 after server-start validation and user-reported stable play. BetterAttachments ergonomics are tuned down from the downloaded high-buff config.

## Install Paths

- Steam EFT: `E:\Steam\steamapps\common\Escape from Tarkov`
- SPT install: `E:\Tarkov-SPT`
- Source mod archive folder: `D:\EFTarkov-mods`
- Original stable snapshot created: `2026-06-28 12:47:45 +08`
- Current accepted modlist updated: `2026-06-29`, after the BetterAttachments and StatRewards layer was accepted.
- Current must-have restore updated: `2026-06-29`, after pitFireTeam was restored again.
- Current stable snapshot saved: `2026-06-29`, before the AutoIFF activation/load-order adjustment.
- Current locked stage saved: `2026-06-29`, after BetterAttachments and StatRewards were accepted.

## Active Server Mods

Location: `E:\Tarkov-SPT\SPT\user\mods`

- `[SVM] Server Value Modifier`
- `BetterAttachments`
- `DPX-ElectronicsCase`
- `EFCL-WelcomeGifts`
- `Infinite-Stash`
- `MergeConsumablesServer`
- `MoreCheckmarksBackend`
- `OldTarkovMovementServer`
- `Refringe-BetterBackpacks`
- `SNACC`
- `SkillsExtended`
- `StatRewards`
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
- `ScrollableAttachments\ScrollableAttachments.dll`
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
- `zzzz-maschine-AutoIFF\maschine-AutoIFF.dll`

## Active BepInEx Patchers

Location: `E:\Tarkov-SPT\BepInEx\patchers`

- `SkillsExtended_PrePatch.dll`
- SPT core patcher `spt-prepatch.dll`

## Stability Tweaks

- `OldTarkovMovementServer\Config\settings.jsonc`: `BotsUseOldMovement` is `false`.
- `SkillsExtended\Resources\Configs\ServerConfig.json`: update check is disabled.
- `com.rpmwpm.UnderFire.cfg`: adrenaline still triggers from suppression, but tunnel vision and tremor are disabled.
- Reduced WTT layer is accepted as `WTT-ServerCommonLib`, `WTT-ClientCommonLib`, and `SNACC` only.
- pitFireTeam is enabled with BigBrain and Waypoints. The startup warning for courier trader `67d3a28a3d6f4f7dbd09ed13` is accepted as long as it remains only a warning and does not block menu or raids.
- New-mod rollback backup from this batch: `E:\Tarkov-SPT\_mod_backups\newmods-20260628-135126`
- AutoIFF config: `com.maschine.AutoIFF.cfg` has `ActivationMode = AlwaysOn`. The prior `Automatic` mode logged `Skipping activation (mode=Automatic, side=Usec)` during PMC raids.
- AutoIFF DLL was moved from plugin root to `BepInEx\plugins\zzzz-maschine-AutoIFF\maschine-AutoIFF.dll` so its path sorts after `pitFireTeam\pitFireTeam.dll`.
- Stable snapshot / AutoIFF rollback backup: `E:\Tarkov-SPT\_mod_backups\stable-autoiff-20260629-064610`
- BetterAttachments config was mass-tuned so existing positive ergonomics buffs target about 10% instead of the downloaded 40-50% range; unchanged categories stayed unchanged. Recoil, heating, and feature toggles were not changed.
- StatRewards is active with default config and local progress data under its mod folder.

## Latest Stable Save - 2026-06-29

User reported the current setup stable so far. Before changing AutoIFF, a rollback snapshot was saved with:

- Active client-plugin manifest.
- Active server-mod manifest.
- BepInEx config files.
- Active profile copy.
- Original root-level `maschine-AutoIFF.dll`.
- Original `com.maschine.AutoIFF.cfg`.

The later BetterAttachments/StatRewards stable report supersedes the earlier AutoIFF fresh-launch caveat.

## Locked BetterAttachments / StatRewards Stage - 2026-06-29

User reported the current setup stable so far after adding BetterAttachments and StatRewards. A rollback snapshot was saved with:

- Active server-mod manifest.
- Active client-plugin manifest.
- Active BepInEx patcher manifest.
- BepInEx config files.
- Active profile copy.
- Tuned BetterAttachments config.
- StatRewards config and progress data.
- Server-start validation evidence.

Snapshot path:

- `E:\Tarkov-SPT\_mod_backups\stable-betterattachments-statrewards-20260629-215157`

Server validation before acceptance:

- Loaded 22 server mods.
- Loaded `BetterAttachments version: 1.0.0`.
- Loaded `StatRewards version: 1.1.1`.
- `StatRewards` loaded 48 milestone definitions.
- `BetterAttachments` updated 1092 attachments.
- Reached `Server has started, happy playing`.
- Existing pitFireTeam courier warning remained the only known warning in the validation evidence.

## Observed Server Mod Load Order

Latest accepted BetterAttachments/StatRewards startup loaded the server mods in this order:

- `BetterAttachments`
- `Show Me The Money`
- `DPX Electronics Case`
- `Welcome Gifts`
- `Infinite Stash`
- `MergeConsumablesServer`
- `MoreCheckmarksBackend`
- `Dynamic Maps`
- `SPTarkovAmmoCases`
- `OldTarkovMovement`
- `Foldables`
- `Instant Insurance`
- `PitFireTeam`
- `BetterBackpacks`
- `Skills Extended`
- `SnaccPack`
- `StatRewards`
- `PostRaidResources`
- `Trader Jeronimo`
- `AirFilter Only Drains In Raid`
- `WTT-ServerCommonLib`
- `SVM`

SPT 4 mod metadata supports dependency information, but most installed server mods in this setup do not expose editable metadata. Prefer dependency/library mods first for new installs, but do not rename live folders just to chase the pitFireTeam courier warning because the same warning appeared during earlier working pitFireTeam runs.

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
- `items-error-packnstrap-20260629-051400`
  - disabled `WTT-PackNStrap`
  - disabled `WTT-PackNStrap` client plugins
  - disabled dependency `UseItemsFromAnywhere.dll`
- `trader-not-found-pitfireteam-20260629-051830`
  - old disabled copy of `pitFireTeam-ServerMod`
  - old disabled copy of `pitFireTeam`
  - old disabled copy of `DrakiaXYZ-BigBrain.dll`
  - old disabled copy of `DrakiaXYZ-Waypoints`
  - this group was later restored again because pitFireTeam is must-have.

## Profile Cleanup Done

- Removed stale `pitFireTeam` trader reference `67d3a28a3d6f4f7dbd09ed13` from the PMC profile.
- Profile backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\remove-pitfireteam-trader-20260628-112108`
- Earlier orphan item cleanup backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\codex-orphan-cleanup-20260628-110653`
- Later removed reintroduced pitFireTeam courier trader profile/dialogue entries after the warning returned.
- Later profile backup: `E:\Tarkov-SPT\_mod_backups\profile-cleanup\trader-not-found-pitfireteam-20260629-051724`
- Restore backup before making pitFireTeam must-have again: `E:\Tarkov-SPT\_mod_backups\restore-pitfireteam-musthave-20260629-052119`
- Current stable profile check after user play: courier ID `67d3a28a3d6f4f7dbd09ed13` is present in `TradersInfo`, absent from `dialogues`, with 0 orphan inventory refs and 0 missing insured refs.
- If pitFireTeam is ever disabled again, remove that courier `TradersInfo` entry before treating the profile as clean.

## Notes

- Keep `DynamicMaps` enabled in this stable baseline; it loaded and worked during the successful test.
- The added QoL/content batch includes inventory/tooling mods plus `traderJeronimo`; if a future profile issue appears, check trader/profile references before broad disabling.
- `pitFireTeam`, `BigBrain`, and `Waypoints` are active and should be kept together.
- `UseItemsFromAnywhere.dll` belongs with the disabled PackNStrap group; do not restore PackNStrap without it.
- Keep AutoIFF in the late-loading `zzzz-maschine-AutoIFF` folder and keep `ActivationMode = AlwaysOn` unless testing Scav-only behavior.
- Do not re-enable `WeekendDrops`, `CaliberUnderName`, `ClearPrepareScreen`, `Handy`, or `RestoreTheOldNumberOfMedicalUses` without testing one at a time.
- Accept the pitFireTeam courier trader warning unless it becomes a real main-menu/profile/raid blocker. Do not disable pitFireTeam without cleaning its courier profile entry.
- If the 60-61% loading-map hang returns, compare against this file first.
