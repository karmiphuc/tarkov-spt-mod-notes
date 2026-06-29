# Tarkov SPT Mod Notes

Sanitized notes for the local SPT setup.

This repo intentionally tracks documentation only. Mod archives, game files, profiles, logs, and generated backups stay local and are ignored.

Current known-good baseline:

- `stable-state-2026-06-28.md`

Historical validation layers folded into the current baseline:

- `pending-commonlib-group-2026-06-28.md`
- `pending-item-qol-2026-06-28.md`
- `pending-welcomegifts-autoiff-scrollable-2026-06-29.md` - stable so far; AutoIFF adjusted to run on PMC and load late.

Pending validation layers:

- `pending-betterattachments-statrewards-2026-06-29.md` - installed and server-start validated; BetterAttachments ergonomics tuned from large buffs down to a mild pending-test config.
- `pending-packnstrap-dpx-useitems-2026-06-29.md` - PackNStrap dependency group disabled after item warnings; DPX remains active.
- `pending-pitfireteam-2026-06-28.md` - restored and treated as must-have.
- `pending-pitfireteam-trader-cleanup-2026-06-29.md` - profile cleanup history; courier warning is accepted while pitFireTeam is enabled.

Rule for future mod testing:

- Keep the stable baseline unchanged.
- Restore or add one disabled mod at a time.
- Run at least one full raid before accepting it into the stable setup.
- Avoid re-enabling `WeekendDrops`, `CaliberUnderName`, `ClearPrepareScreen`, `Handy`, or `RestoreTheOldNumberOfMedicalUses` in bulk.
- Keep pitFireTeam, BigBrain, and Waypoints together; pitFireTeam is a must-have for this setup.
- The pitFireTeam courier `Trader not found` startup warning is known and accepted as long as the server reaches `Server has started, happy playing`. If pitFireTeam is disabled again, clean courier ID `67d3a28a3d6f4f7dbd09ed13` from the profile.
- Prefer library/dependency mods first when adding new server mods. Do not rename live mod folders or force order changes unless a real dependency error appears.
- AutoIFF should stay in `BepInEx\plugins\zzzz-maschine-AutoIFF\` with `ActivationMode = AlwaysOn`; default `Automatic` skips activation while playing PMC.
- Treat `UseItemsFromAnywhere.dll` as part of the WTT PackNStrap dependency group. Restore or disable it together with `WTT-PackNStrap`.
