<div align="center">

# VladModelViewer

A World of Warcraft model viewer focused on **3.3.5a (Wrath of the Lich King)** and private-server content.

[![License: GPL v3](https://img.shields.io/badge/license-GPL%20v3-blue.svg)](LICENSE.md)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)](#)
[![Built with Qt 6](https://img.shields.io/badge/Qt-6-41CD52.svg)](https://www.qt.io)
[![Version](https://img.shields.io/badge/version-0.5.2-orange.svg)](#)

</div>

---

## About

VladModelViewer is a desktop tool for browsing, inspecting, and exporting assets from World of Warcraft client data. It is tuned for back-ported and custom-server content, with particular attention to private-server workflows.

It is a fork of [Frostshake/WMVx](https://github.com/Frostshake/WMVx) with additional work on stability, WMO support, and quality-of-life features.

## Highlights

- Native Qt 6 viewer with hardware-accelerated rendering
- Reads MPQ archives directly via StormLib &mdash; no client modification required
- Recursive scanning of custom patch folders for private-server setups
- WMO (world map object) loading and inspection
- Persistent file-index cache for instant launches after the first scan
- Quick screenshots and bulk MPQ extraction
- Noggit Red integration for "drop last loaded model" workflows
- Crash dumps and live logging for clean bug reports

## Quickstart

1. **Unzip** this folder anywhere on your drive (e.g. `C:\Tools\VladModelViewer`).
2. **Run** `VladModelViewer.exe`.
3. The **Choose Client** dialog opens. Click **Browse** and pick the root folder of your WoW 3.3.5 install &mdash; the one that contains the `Data\` subfolder.
4. Click **Load**. The first scan takes about 30&ndash;90 seconds while the app reads every archive's listfile. Every launch after that is instant via the cache.
5. Tick **Remember these options** before Load if you want to skip the client picker next time. You can change this from **File &rarr; Settings** at any point.

## Adding Custom Patch Folders

If you have additional MPQs outside your main client (Warsworn, WarcraftDraft, custom patches):

1. Open **File &rarr; Settings**.
2. Add the folder path under **Extra MPQs** &mdash; one folder per line.
3. The app scans each folder recursively for `*.mpq` files and merges them into the file list.

## Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Ctrl` + `O` | Open the **Load Client** picker dialog |
| `Ctrl` + `F` | Focus the file-search box |
| `F` | Fit camera to all loaded models |
| `F10` | Quick screenshot to `screenshots\` |

## Runtime Files

These are created next to the executable on first use. All are safe to delete &mdash; they regenerate automatically.

| Path | Purpose |
| :--- | :--- |
| `cache/` | File-index cache (speeds up subsequent launches) |
| `logs/wmvx.log` | Live application log |
| `logs/crashes/` | Crash dumps and `crashlog.txt` |
| `screenshots/` | Quick screenshots from `F10` |
| `userSettings/log.txt` | Noggit Red integration log |
| `export/` | Bulk MPQ extraction output |
| `settings.ini` | User preferences |
| `favorites.json` | Starred files |

## Noggit Red Integration

The viewer writes `userSettings\log.txt` in WMV-compatible format. Point Noggit Red's **WMV log path** setting at that file, and Noggit's **Drop last loaded WMV model** command will pick up the most recently loaded model from this viewer.

## Bug Reports

If something crashes or renders incorrectly, the most useful artifacts are:

- `logs\wmvx.log`
- Any `logs\crashes\crashdump_*.dmp` from the same session

[Open an issue](../../issues/new) with those attached and a short description of what you were loading.

## Built With

- [Frostshake/WMVx](https://github.com/Frostshake/WMVx) &mdash; upstream model viewer
- [StormLib](http://www.zezula.net/en/mpq/stormlib.html) by Ladislav Zezula &mdash; MPQ archive access
- [Qt 6](https://www.qt.io) &mdash; application framework

## License

Released under the **GNU General Public License v3.0**. See [LICENSE.md](LICENSE.md) for the full text.
