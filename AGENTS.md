# Sofle Keyboard Workspace

## Current Hardware

- Keyboard target: `sofle/rev1`.
- Controllers: RP2040 boards with a Pro Micro-compatible footprint.
- Converter: `sparkfun_pm2040`, set in the personal keymap's `rules.mk`.
- Do not build or flash the default AVR/Caterina target.
- Both halves were flashed successfully on 2026-09-24.
- VIA protocol 13 is enabled with five dynamic layers; use `https://usevia.app`.
- Vial is not enabled.

## Personal Keymap

- Work only in `keyboards/sofle/keymaps/dsilva/` unless a broader QMK change is explicitly requested.
- The current baseline is copied from QMK's default Sofle keymap.
- It includes QWERTY, Colemak, `LOWER`, `RAISE`, combined `ADJUST`, OLED support, and encoder controls.

## Saved VIA Layouts

- Main Sofle: `keyboards/sofle/keymaps/dsilva/layouts/main_sofle_layout.json`
- Ninja Sofle: `keyboards/sofle/keymaps/dsilva/layouts/ninja_sofle_layout.json`

## Commands

```bash
qmk compile -kb sofle/rev1 -km dsilva
qmk flash -kb sofle/rev1 -km dsilva
```

Flash both halves separately after firmware changes. Connect USB directly to the half being flashed.

To enter the RP2040 bootloader, run `qmk flash` first so it is waiting for `RPI-RP2`, then double-tap the physical reset button on the directly USB-connected half. The controller should appear as `RPI-RP2` and the UF2 will copy automatically.

Connect USB to the physical left half for normal use. Direct USB on the physical right half is for flashing only; without persistent side identification its keys can map as the left half, so do not rely on a key chord to enter bootloader.

Never connect or disconnect the TRRS cable while either half has USB power. Unplug USB before moving cables.

Do not commit generated `.uf2`, `.hex`, `.bin`, `.elf`, or `.build/` artifacts.
