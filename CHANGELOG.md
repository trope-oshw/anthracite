# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
extended with a **Hardware** / **Firmware** / **Errata** / **Documentation**
split, because hardware and firmware move at different speeds.

Versioning is described in the README. In short: the product and the boards
carry `vMAJOR.MINOR`, the firmware carries its own semantic version, and the
two are listed together for each release.

## [1.1.0] - 2026-11-11

### Hardware
Top board:
- R96 and R97 (100 MΩ) added in series with R38 and R86: the gate resistor
  of each output JFET switch is now 200 MΩ, as described in ERRATA M-1.
- RV2 and RV3 (Bass, Treble) changed from 20kB to 25kB. R75 and R77 changed
  from 1 kΩ to 2.7 kΩ, R76 and R78 from 1.5 kΩ to 390 Ω, to keep the v1.0
  tone response (within 0.2 dB, simulated).
- U4 changed from TLV9362IDR to OPA1678IDR.
- Soft start on the input supply: D30, C51 and R95 added; D3 changed from
  BZT52C15 to BZT52C13.
- J9 (JST ZH, 2-pin) added to sense the supply voltage after the DC jack.
- Measurement header J8 reassigned and J10 added. J8 and J10 are not fitted
  on production units. R74 removed.
- D1 (not fitted) changed from MMSZ5245B to BAS416.
- Now assembled by the board house instead of by hand: Q1, Q3, U2, U4, C13,
  C23, C28, C41, C47, C49, J6. C13, C23, C47 and C49 are now 25MU105MA23216,
  and J6 is A1001WR-S-04PD01.
- The default footprint of the 2SK880-GR symbol now names an existing
  footprint (symbol metadata only).

Bottom board:
- MIDI OUT driver: Q103 replaced by two 74HCT04 inverters in series (U107A,
  U107B) driving the Tip through Schottky diode D118. This removes the delay
  caused by the storage time of Q103.
- D116 and D117 (BAV99) clamp the Tip and Ring of J104.
- R144 (470 Ω) added between U109 and the Tip. The reference R144 is reused:
  on v1.0 it was the 3.3 kΩ resistor for LED D115.
- R128 (220 Ω) moved to 0603. R131 changed from 120 Ω 0402 to 100 Ω 0603.
- Removed: Q103, U108, R125, R126, C137, D115 with the old R144, and the
  measurement header J106.

Both boards:
- The published boards carry `v1.1`, CERN-OHL-S-2.0 and the repository URL
  on the silkscreen.

### Firmware
- 1.1.0, for Anthracite v1.1 boards only. v1.0 boards keep 1.0.0, which
  stays available at tag `firmware-1.0.0`. Do not load 1.0.0 onto a v1.1
  board: v1.1 has no hardware gate between the MIDI OUT driver and the Tip,
  and 1.0.0 relied on that gate for `MSEND` and for a byte still being sent
  when DIP-SW3 is turned off.
- The firmware keeps MIDI OUT silent while DIP-SW3 is off: no Thru, no Active
  Sensing, and the serial console's `MSEND` command replies `ERR LATCH`. The
  exception is the console's DBG mode; see firmware/README.md.
- Changed: at power-on and when DIP-SW3 changes, the external-switch input is
  now read after its pull-up is connected and has settled for 2 ms.
- Added: with DIP-SW3 and DIP-SW4 off, a new Tip level must hold for 5 ms
  before the signal path switches (debounce).
- PB6 (USART1 TX) gets its internal pull-up after UART initialisation.
- The serial console's boot banner reports the firmware version
  (`BOOT anthracite-1.1.0 ...`).
- Source comments corrected: the Offset bias ratio is 2:1, and the MIDI OUT
  stage is described as built on v1.1.
- The `Debug` preset reproduces the image on v1.1 units: 42,680 bytes,
  SHA-256 `c3b4315e...d338`. See firmware/README.md.

### Errata
- None known at release.

### Documentation
- Schematic PDFs and PNGs moved into `docs/schematics/pdf/` and
  `docs/schematics/png/`.
- Bills of materials moved into `docs/bom/`.
- README rewritten for v1.1: controls with measured plots, the MIDI CC
  table and the specifications. A Japanese version is in `README.ja.md`.
- CONTRIBUTING rewritten, with a Japanese version in `CONTRIBUTING.ja.md`.
- The trademark terms moved from the README into `TRADEMARK.md`, with a
  Japanese version in `TRADEMARK.ja.md`.
- [hardware/parts.md](hardware/parts.md) updated for v1.1.
- BOM datasheet links now point to the part maker's datasheet or to LCSC;
  links to shop pages were removed. Part descriptions corrected, including
  U106, which is an EEPROM.
- ERRATA M-1 notes that v1.1 includes the change.
- Schematic notes no longer quote measured values.

## [1.0.0] - 2026-10-07

First public release.

### Hardware
- Anthracite v1.0. Analogue signal path throughout, switched by analogue
  switches rather than mechanical contacts, with a buffered bypass.
- Three circuit boards: top (analogue), bottom (control) and footswitch, plus
  the front-panel artwork.
- Four potentiometers (Volume, Fuzz, Bass, Treble) and three-position toggles
  for Bias, Response and Input.
- The published top and bottom boards carry `V1.0`, CERN-OHL-S-2.0 and
  `github.com/trope-oshw/anthracite` on the silkscreen in place of the product
  name. Boards from the first production run carry `Anthracite V1.0` instead.
- The NMJ6HCD3 symbol stored in the top schematic names the same footprint
  as J5, J7 and the board. Only that symbol metadata changed; the board, the
  Gerbers and the BOM match the shipped boards.

### Firmware
- 1.0.0. MIDI CC control of the toggles, MIDI-Learn, MIDI Thru, and Active
  Sensing output.
- Source in `firmware/`: the STM32CubeMX project, the CMake build, and the ST
  HAL and CMSIS. The `Debug` preset reproduces the shipped flash image; see
  [firmware/README.md](firmware/README.md) for the toolchain and the SHA-256.

### Errata
- None known at release.

### Documentation
- User manual published at https://docs.trope-oshw.org
- Parts list in [hardware/parts.md](hardware/parts.md).
- README product photo: a top view of the finished pedal, plus angled, top
  edge and side views.

[1.1.0]: https://github.com/trope-oshw/anthracite/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/trope-oshw/anthracite/releases/tag/v1.0.0
