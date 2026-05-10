VladModelViewer 0.5.2
=====================

A WoW Model Viewer focused on World of Warcraft 3.3.5a (Wrath of the Lich
King) and back-ported / custom-server content. Forked from Frostshake/WMVx
and enhanced for stability, WMO support, and quality-of-life on private
servers.


QUICKSTART
----------

1. Unzip this folder to anywhere on your drive (e.g. C:\Tools\VladModelViewer).
2. Run VladModelViewer.exe.
3. The "Choose Client" dialog opens. Click Browse and pick the root folder
   of your WoW 3.3.5 install (the folder that contains the Data\ subfolder).
4. Click Load. First scan takes ~30-90 seconds while the app reads every
   archive's listfile; every launch after that is instant via the cache.
5. Tick "Remember these options" before Load if you want to skip the
   client-picker on future launches. You can untick it any time from
   File > Settings.


ADDING CUSTOM PATCH FOLDERS
---------------------------

If you have additional MPQs in a folder outside your main client (e.g.
custom Warsworn / WarcraftDraft patches), open File > Settings and add
the folder path under "Extra MPQs". One folder per line; the app scans
each recursively for *.mpq files and merges them into the file list.


WHAT GETS GENERATED AT RUNTIME
------------------------------

The app creates these folders next to the exe on first use. Safe to
delete; they regenerate.

  cache/         - file-index cache (speeds up subsequent launches)
  logs/          - wmvx.log live application log
  logs/crashes/  - crash dumps and crashlog.txt for diagnostics
  screenshots/   - F10 quick screenshots
  userSettings/  - log.txt for Noggit Red integration (model drop)
  export/        - bulk MPQ extraction output
  settings.ini   - your preferences
  favorites.json - your starred files


KEYBOARD SHORTCUTS
------------------

  Ctrl+O     Load Client (opens the picker dialog)
  Ctrl+F     Focus the file-search box
  F          Fit camera to all loaded models
  F10        Quick screenshot to screenshots\


NOGGIT RED INTEGRATION
----------------------

The app writes userSettings\log.txt in WMV-compatible format. Point
Noggit Red's "WMV log path" setting at that file and Noggit's
"Drop last loaded WMV model" command will pick up the most recently
loaded model from this viewer.


LICENSE
-------

GNU GPL v3. See LICENSE.md for the full text. Source code at
https://github.com/VladProject/VladModelViewer (or wherever the
upstream repo lives at the time of distribution).

Built on:
  - Frostshake/WMVx (https://github.com/Frostshake/WMVx)
  - Ladislav Zezula's StormLib
  - The Qt Framework (https://www.qt.io)


BUG REPORTS
-----------

If something crashes or renders incorrectly, the most useful artifact
is the contents of logs\wmvx.log plus any logs\crashes\crashdump_*.dmp
file from the same session. Send those along with a short description
of what you were loading at the time.
