# KOF XIII Trainer + Hitboxes

Combined trainer and automatic hitbox viewer for **KOF XIII GLOBAL MATCH (Windows)** by KOFCOMBO / PERFECTCOMBO.

## Download

Download **KOF13-Trainer-Hitboxes-Beta3.zip** from [Beta 3](https://github.com/PERFECTCOMBO/KOFXIII-Trainer-Hitboxes/releases/tag/v0.2.0-beta.3). Choose that file under Assets, not the automatic Source code archives.

**Prerelease:** installation, restoration, Lua preservation and DLL forwarding checks passed. In-game testing of this compatibility build is still pending. Online match compatibility is unverified.

## Compatibility

Beta 3 automatically detects:

- A supported clean game, including unrelated asset mods.
- **KOF XII Six-Stage Pack Build 83**: keeps its stage/victory functions and stage-lighting DLL.
- An existing standalone **Trainer + Hitboxes Beta 2** installation.

Unrelated stage artwork, previews, audio, recordings and viewer settings are preserved. Mods editing the same shared scripts, practice menu/stats or input DLL need a compatible merge. Unknown shared-file conflicts are rejected before writes. This is not universal compatibility with every mod.

## Install

1. To use both mods, install the full **six-stage Build 83 pack first**, then this trainer. The trainer ZIP does not include stage artwork.
2. Extract the complete trainer ZIP into a folder outside the game folder. Keep its files together.
3. Close XIII and the hitbox viewer.
4. In Steam, choose **Manage > Browse local files**. Copy the path of the folder containing game.exe.
5. Run **INSTALL.cmd**, paste the game folder and wait for **installed and verified**.
6. Launch XIII normally. The viewer starts automatically in the background.
7. In offline Training, use **LP+LK / LP+HP** to switch pages. Page 4 > **HITBOX VIEWER** turns it on.

If access is denied, run INSTALL.cmd as administrator. Do not drag payload files into the game folder: that bypasses compatibility checks and backup.

**Install order matters:** do not copy the stage pack's main.lua or dinput8.dll over the combined installation. To add stages to a trainer-only install, restore the trainer, install Build 83, then reinstall the trainer. Restore the trainer before updating stages.

## Features

- Four offline training pages with restart-position, play-side and HUD controls.
- Large and small training stats panels.
- Record Dummy, Stop / Playback, Play Recording and Loop Recording, with icons and five saved recording slots.
- Hitbox viewer On/Off and attack-hitbox, hurtbox and pushbox filters.
- Fill: Outline / Light / Dense. Box Labels: On / Off.
- Frame-data panels, timing meter and on-screen legend removed.
- Hitbox master turns off through the patched training exits; filter preferences remain.
- F8 toggles the overlay, F9 opens display settings, F3 cycles fill. Viewer hides when the game loses focus.
- Online waiting practice retains two pages, SELECT BUTTON, Player Match Menu and Return to Room. Custom recording/hitbox controls are for offline Training.
- Menu-value, command, icon-alignment and hidden-divider panel-stretch fixes through Test 61.

## Recording slots

Let recordings finish the full **10 seconds** before saving. In a fresh session, make a full-length recording before loading a full saved slot.

**LENGTH MISMATCH** means the saved/current recording buffers differ. This version refuses that load; shorter recordings are not resized. Saving replaces the selected slot and keeps its previous save as a .bak.

## Backup and restore

INSTALL creates **_KOF13TrainerHitboxesBeta3_Backup** in the game folder. Keep it. This is a mod-file backup, not a Windows system restore point.

To uninstall, close XIII/viewer, run **RESTORE.cmd**, and select the same game folder. It restores the exact pre-install files, preserves personal recordings/settings, and refuses to overwrite newer shared-file changes. Restoring a Build 83 integration leaves Build 83 installed.

**Beta 2 upgrades:** keep both backup folders. Restoring Beta 3 returns to Beta 2. Use the Beta 2 package and its original backup to remove Beta 2 afterward. Uninstall in reverse installation order; never use someone else's backup.

## Report problems

Please [open an issue](https://github.com/PERFECTCOMBO/KOFXIII-Trainer-Hitboxes/issues) with:

- Trainer version and game version.
- Offline Training or online waiting-practice mode.
- Other mods, including the stage-pack build.
- Steps, expected result, actual result and exact error.
- Screenshot/video if possible; for connection errors, include the message in F9.

Avoid sharing personal information in logs/screenshots.

## Credits

Original hitbox-viewer and Dear ImGui license notices are included in the ZIP's licenses folder. Original game/stage artwork belongs to SNK. This is an unofficial community mod.
