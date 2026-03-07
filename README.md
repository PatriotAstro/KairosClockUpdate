# KairosClock Standalone Web Flasher

This page flashes KairosClock over USB serial in Chrome/Edge, even for older firmware.

## Files

- `index.html`
- `manifest.json` (full-stack flash)
- `bootloader.bin`
- `partitions.bin`
- `boot_app0.bin`
- `firmware.bin`
- `spiffs.bin`

## Build + copy bins from this project

From project root:

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\prepare_webflasher_package.ps1
```

## Host it

Host the `webflasher` folder over `https://` (GitHub Pages, Netlify, etc).

## User requirements

- Chrome or Edge desktop
- USB data cable

## Notes

- Flash offsets match this project partition layout:
  - bootloader: `0x1000`
  - partitions: `0x8000`
  - boot_app0: `0xE000`
  - app: `0x10000`
  - spiffs: `0x290000`
- This web flasher performs a full-stack update (recovery style).
- On some devices this can clear stored settings (NVS behavior depends on prior partition/layout state).
