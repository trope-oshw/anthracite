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

## [1.0.0] - 2026-XX-XX

First public release.

### Hardware
- Anthracite v1.0. Analogue signal path throughout, switched by analogue
  switches rather than mechanical contacts, with a buffered bypass.
- Three boards: top (analogue), bottom (control), and the front panel.
- Four potentiometers (Volume, Fuzz, Bass, Treble) and three-position toggles
  for Bias, Response and Input.

### Firmware
- 1.0.0. MIDI CC control of the toggles, MIDI-Learn, MIDI Thru, and Active
  Sensing output.

### Errata
- None known at release.

### Documentation
- User manual published at https://docs.trope-oshw.org

[Unreleased]: https://github.com/trope-oshw/anthracite/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/trope-oshw/anthracite/releases/tag/v1.0.0
