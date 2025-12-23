# Windows Language Pack Deployment Tool

A self-contained Python utility for discovering, downloading, and installing
Windows language packs (Language Experience Packs, CAB language packs, and
Features on Demand) on Windows 10 / 11 systems.

Or use the compiled exe.

---

## Features

- **Does NOT rely on Windows Update, Microsoft Store, or UWP services**
  - Uses direct package installation (DISM + provisioning)
  - Works on LTSC / stripped-down systems
- Interactive language selection (common languages prioritized)
- Automatic architecture detection (x86 / x64 / ARM64)
- Installs:
  - Language Experience Packs (APPX)
  - Core language CAB packages
  - Features on Demand (OCR, TTS, fonts)
- Applies language to user, system, and login screen

---

## Requirements

- Windows 10 or Windows 11
- Python 3.9+
- Administrator privileges
- Internet access

---

## Python Dependencies

```
pip install rich questionary
```

---

## Required Files

Place the following files in the same directory as the script:

- `win10LangExpPacks.dat`
- `win10FoD.dat`
- `win10LangOpts.dat`

These files must contain URL lists pointing to official Microsoft language
resources (APPX, CAB, license XML).

---

## Usage

### Normal run (install mode)

```
python deployLangs.py
```

### Dry-run mode (no installation)

```
python deployLangs.py --dry-run
```

---

## Notes

- A reboot is required for language changes to fully apply
- DISM may report `RestartNeeded : False` even when reboot is still required
- WinPE language packages are ignored automatically
- No silent reboots are performed

---

## License

Maybe Not
