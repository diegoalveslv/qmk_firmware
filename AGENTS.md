# Sofle Keyboard Workspace

## Current Hardware

- Keyboard target: `sofle/rev1`.
- Controllers: RP2040 boards with a Pro Micro-compatible footprint.
- Converter: `sparkfun_pm2040`, set in the personal keymap's `rules.mk`.
- Do not build or flash the default AVR/Caterina target.
- Both halves were flashed successfully on 2026-09-24.

## Personal Keymap

- Work only in `keyboards/sofle/keymaps/dsilva/` unless a broader QMK change is explicitly requested.
- The current baseline is copied from QMK's default Sofle keymap.
- It includes QWERTY, Colemak, `LOWER`, `RAISE`, combined `ADJUST`, OLED support, and encoder controls.

## Commands

```bash
qmk compile -kb sofle/rev1 -km dsilva
qmk flash -kb sofle/rev1 -km dsilva
```

Flash both halves separately after firmware changes. Connect USB directly to the half being flashed.

To enter the RP2040 bootloader reliably, unplug USB, hold the top-left physical key on that half, reconnect USB, hold for three seconds, then release. The controller should appear as `RPI-RP2`.

Never connect or disconnect the TRRS cable while either half has USB power. Unplug USB before moving cables.

Do not commit generated `.uf2`, `.hex`, `.bin`, `.elf`, or `.build/` artifacts.
