# KairosClock Standalone Web Flasher

This page flashes KairosClock over USB serial in Chrome/Edge, even for older firmware.

## Files

- `index.html`
- `manifest.json`
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
  - app: `0x10000`
  - spiffs: `0x13C000`
