# Pending Item Info QoL - 2026-06-28

Status: accepted into the stable baseline after user raid validation.

## Purpose

Help a new player decide what to keep or sell without checking a wiki constantly.

- `Show Me The Money` shows item sell/value information for money decisions.
- `MoreCheckmarks` shows quest, hideout, barter, craft, and wishlist usefulness for progression decisions.

## Installed Mods

Server mods added:

- `com.swiftxp.spt.showmethemoney` - Show Me The Money `2.7.0`
- `MoreCheckmarksBackend` - MoreCheckmarks backend `2.2.0`

Client plugins added:

- `com.swiftxp.spt.showmethemoney\SwiftXP.SPT.ShowMeTheMoney.Client.dll`
- `MoreCheckmarks\MoreCheckmarks.dll`
- `MoreCheckmarks\MoreCheckmarksAssets`

Source archives saved locally:

- `D:\EFTarkov-mods\swiftxp-showmethemoney-2.7.0.7z`
  - SHA256: `8e79ccd33d52a72f33ff0a2b10cc390b1b5a685f3dbf5c7d4b6c0b7852ef8094`
- `D:\EFTarkov-mods\MoreCheckmarks-v2.2.0.7z`
  - SHA256: `1a869c4b05c950a6d502ab37721897784c216957a8ededb27a6380cd6e973309`

Pre-install rollback backup:

- `E:\Tarkov-SPT\_mod_backups\itemqol-20260628-152107`

## Verification

SPT server startup:

- Loaded 15 server mods.
- Loaded `Show Me The Money version: 2.7.0`.
- Loaded `MoreCheckmarksBackend version: 2.2.0`.
- Logged `MoreCheckmarks data loaded.`
- Reached `Server has started, happy playing`.

Launcher:

- Connected to `https://127.0.0.1:6969`.
- Reported `SPT MatchingVersion: 4.0.13`.

Accepted:

- EFT client-side plugin load after pressing Play.
- User reported the later combined setup stable; this layer is now listed in `stable-state-2026-06-28.md`.
