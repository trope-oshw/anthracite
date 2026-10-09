# Changelog

All notable changes to this project are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
extended with a **Hardware** / **Firmware** / **Errata** / **Documentation**
split, because hardware and firmware move at different speeds.

Versioning is described in the README. In short: the product and the boards
carry `vMAJOR.MINOR`, the firmware carries its own semantic version, and the
two are listed together for each release.

## [Unreleased]

### Hardware
- (nothing yet)

### Firmware
- (nothing yet)

### Errata
- See [ERRATA.md](ERRATA.md)

### Documentation
- (nothing yet)

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
  name. Boards from the first production run carry `Anthracite V1.0` instead
  and are otherwise identical.
- The NMJ6HCD3 symbol stored in the top schematic now names the same footprint
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

[Unreleased]: https://github.com/trope-oshw/anthracite/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/trope-oshw/anthracite/releases/tag/v1.0.0
