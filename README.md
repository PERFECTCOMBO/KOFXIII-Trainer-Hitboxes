# KOF XIII Trainer + Hitboxes

Combined trainer and automatic hitbox viewer for **THE KING OF FIGHTERS XIII GLOBAL MATCH (Windows)** by KOFCOMBO / PERFECTCOMBO.

## Download

Get **KOF13-Trainer-Hitboxes-Beta2.zip** from [Releases](https://github.com/PERFECTCOMBO/KOFXIII-Trainer-Hitboxes/releases). Download that ZIP under Assets, not GitHub's automatic Source code archive.

**Beta 2 is a prerelease.** Installer/restore, file-integrity and automatic-launch checks passed. A clean-install in-game smoke test is still pending, and online match compatibility has not been verified.

## Requirements

Use a clean, supported Windows GLOBAL MATCH installation. The installer checks the executable and required original files before changing anything.

Do **not** install over the six-stage pack, another training mod, or an existing dinput8.dll/recording DLL mod. This standalone package does not include the stage pack. Conflicting or unsupported files are refused.

## Install

1. Extract the entire ZIP into a normal folder **outside the game folder**. Keep all files together.
2. Close XIII and the hitbox viewer.
3. In Steam, choose **Manage > Browse local files** for XIII. Copy the folder path containing game.exe.
4. Run **INSTALL.cmd** and paste that path when asked.
5. Wait for **installed and verified**, then launch the game normally.
6. Open offline Training. Use **LP+LK / LP+HP** to change pages; on page 4, set **HITBOX VIEWER** to ON.

If access is denied, run INSTALL.cmd as administrator. Do not drag the payload directly into the game folder: that bypasses the checks and backup.

The viewer starts automatically in the background. Its EXE and the DLLs are internal parts of the combined package; no separate viewer install is needed.

## Features

- Four offline training-menu pages, restart-position/play-side controls and HUD controls.
- Large and small training stats displays.
- Record Dummy, Stop / Playback, Play Recording and Loop Recording with action icons.
- Five recording slots with save/load.
- Hitbox viewer On/Off; attack hitbox, hurtbox and pushbox filters.
- Fill: Outline / Light / Dense. Box Labels: On / Off.
- Frame-data panels, timing meter and on-screen legend removed.
- Hitbox master switch turns off through the patched training exits; filter settings remain.
- F8 toggles hitboxes, F9 opens viewer display settings, F3 cycles fill. Overlay hides when the game loses focus.
- Online waiting practice keeps the original two pages, SELECT BUTTON, Player Match Menu and Return to Room. Custom recording and hitbox controls are for offline Training.
- Includes menu-value, common-command, icon-alignment and hidden-divider panel-stretch fixes.

## Recording slots

Let a recording finish the full **10 seconds** before saving. In a fresh session, make a full 10-second recording before loading a full saved slot.

**LENGTH MISMATCH** means the saved and current recording buffers have different lengths. This version refuses that load; it does not resize shorter recordings. Saving overwrites the selected slot and keeps its previous save as a .bak.

## Backup and restore

INSTALL creates **_KOF13TrainerHitboxesBeta2_Backup** inside the game folder. Keep it: it contains your pre-install files and checksums. This is a mod-file backup, not a Windows system restore point.

To uninstall:

1. Close XIII and the viewer.
2. Run **RESTORE.cmd** from the extracted package.
3. Select the same game folder.

Restore puts back the original pre-install files and removes newly added package files. Personal recordings and viewer settings are preserved. If installed files have changed since installation, restore stops instead of overwriting a newer mod. Do not use somebody else's backup.

## Report problems

Please [open an issue](https://github.com/PERFECTCOMBO/KOFXIII-Trainer-Hitboxes/issues) if something breaks. Include:

- Package version: **Trainer + Hitboxes Beta 2**.
- Game version and mode: offline Training, online waiting practice, etc.
- Exact steps, what you expected, and what happened.
- Error text and any other installed mods.
- A screenshot or short video if possible. For connection problems, include the error shown in F9.

Please avoid including personal paths or account details in screenshots/logs.

## Credits

Original hitbox-viewer and Dear ImGui license notices are included in the ZIP's **licenses** folder. This is an unofficial community mod, not an SNK product.
