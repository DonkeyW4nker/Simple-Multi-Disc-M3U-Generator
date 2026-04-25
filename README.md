# M3U Generator

Build, edit, and bulk-generate `.m3u` playlists for multi-disc games.

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

A modern Tkinter GUI for stitching multi-CD games (PlayStation, Saturn, Sega CD, Dreamcast, etc.) into single emulator-ready playlists.

## Quick start

**Windows:** Download `M3UGenerator.exe` from the [latest release](../../releases/latest) and run it. No install needed.

**macOS / Linux:** Run from source:
```bash
python3 m3u_generator.py
```
Requires Python 3.10+. Tkinter is bundled — no extra packages.

## Three modes

**Generate** — pick 2–15 disc files, choose a path mode, and create a fresh playlist.

**Edit** — open any existing `.m3u` file and reorder, add, or remove discs, then save back over it (or to a new path).

**Bulk** — point at a folder of ROMs, get one `.m3u` per detected multi-disc game in a single pass.

## Features

- Add 2–15 disc files at once, reorder, delete with confirmation
- **Two path modes**
  - **Relative paths** — keeps your ROMs in their existing folders
  - **Filename only** — auto-creates a `Game.m3u/` subfolder; standard for RetroArch, DuckStation, BizHawk
- **Format validation** — only allows known emulator-compatible extensions; warns on mixed format types or filename mismatches
- **Light / dark theme** toggle
- **Hover tooltips** and a built-in help page documenting every action

## Supported formats

`.cue` `.iso` `.chd` `.ccd` `.pbp` `.gdi` `.cdi` `.rvz` `.gcz`

The in-app **?** help page shows the full compatibility matrix by console.

## Building the executable yourself

The project ships with a one-click build script that produces a single, self-contained `.exe` with the custom icon embedded.

### Windows

1. Open a terminal (`cmd` or PowerShell) inside the project folder
2. Run:
   ```
   build.bat
   ```
3. When it finishes, the executable appears at `dist\M3UGenerator.exe`

The script will:
- Auto-install PyInstaller if not present
- Build a single-file windowed `.exe` (no console window)
- Embed `m3u_icon.ico` as the file-manager icon
- Bundle the icon as a runtime resource (so the title bar and taskbar show it too)

### Manual build (any OS)

If you'd rather invoke PyInstaller directly:

```bash
pip install pyinstaller
pyinstaller --onefile --windowed --icon m3u_icon.ico --add-data "m3u_icon.ico;." m3u_generator.py
```

Output appears in `dist/`.

## Files

| File | Purpose |
|------|---------|
| `m3u_generator.py` | Main application |
| `m3u_icon.ico`     | Window, taskbar, and file-manager icon |
| `build.bat`        | One-click Windows build script |
| `README.md`        | This file |
| `LICENSE`          | MIT |

## License

MIT — see [LICENSE](LICENSE).
