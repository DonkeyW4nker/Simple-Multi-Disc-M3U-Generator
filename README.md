# M3U Generator

A clean, modern desktop tool for building **multi-disc `.m3u` playlists** from ROM disc files. Designed for emulator users who need to bundle multi-CD games (PlayStation, Saturn, Sega CD, Dreamcast, etc.) into single, swappable playlists.

[![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/DonkeyW4nker/Simple-Multi-Disc-M3U-Generator/blob/main/LICENSE)

---

## Features

- **Add 2–15 disc files** with multi-select file picker
- **Reorder** discs (↑ / ↓ buttons)
- **Delete** discs
- **Two path modes**
  - **Relative paths** — for portable setups where the M3U sits with the ROMs in their existing folder
  - **Filename only** — auto-creates a `Game.m3u/` subfolder; ideal for RetroArch / DuckStation / BizHawk
- **Bulk mode** — point at a folder of ROMs and generate one M3U per detected multi-disc set automatically
- **Format validation** — only allows known emulator-compatible formats; warns on mixed format types or possible filename mismatches
- **Light / dark theme** toggle
- **Built-in help page** with format compatibility by console

## Supported formats

`.cue` `.iso` `.chd` `.ccd` `.pbp` `.gdi` `.cdi` `.rvz` `.gcz`

See the in-app **?** help page for the full compatibility matrix by console.

---

## Running

### Option 1 — Pre-built executable (Windows)

Download `M3UGenerator.exe` from the [latest release](../../releases/latest) and double-click. No Python install required.

### Option 2 — From source

Requires **Python 3.10+** (Tkinter is bundled with Python; no extra packages needed).

```bash
# Windows
python m3u_generator.py

# macOS / Linux
python3 m3u_generator.py
```

---

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
- Build a single-file windowed `.exe`

### Manual build (any OS)

If you'd rather invoke PyInstaller directly:

```bash
pip install pyinstaller
pyinstaller --noconfirm --clean m3u_generator.spec
```

Output appears in `dist/`.

---

## Files

| File | Purpose |
|------|---------|
| `m3u_generator.py`   | Main application |
| `m3u_icon.ico`       | Window, taskbar, and file-manager icon |
| `build.bat`          | One-click Windows build script |
| `m3u_generator.spec` | PyInstaller build configuration |
| `README.md`          | This file |
| `LICENSE`            | MIT |

## License

MIT — see [LICENSE](LICENSE).
