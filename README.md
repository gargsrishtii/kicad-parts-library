# Srishti's KiCad Parts Library

Custom KiCad symbols and footprints for components missing from the official
KiCad libraries, built and verified while working on embedded systems / IoT
projects.

## Why this exists

Some parts (especially modules from smaller manufacturers, or dev boards not
in the default libraries) aren't available in KiCad's default libraries or
on SnapEDA/EasyEDA in a verified form. This repo collects symbols and
footprints I've built and verified against datasheets/manufacturer data, so
they're reusable for future projects and for anyone else who needs them.

## Contents

| Part | Manufacturer | Package | Source |
|---|---|---|---|
| RYLR998 | REYAX | 5-pin castellated SMD, 2.54mm pitch | [Datasheet](https://reyax.com/upload/products_download/download_file/RYLR998_EN.pdf) |
| ESP32-DEVKITC-VE | Espressif | 38-pin dual row THT header, 2.54mm pitch, 25.4mm row spacing | [Espressif Docs](https://docs.espressif.com/projects/esp-dev-kits/en/latest/esp32/esp32-devkitc/user_guide.html) |

## How to use this library in KiCad

1. Clone or download this repo to your computer
2. Open KiCad -> Preferences -> Manage Symbol Libraries
3. Global Libraries tab -> click "+" -> set:
   - Nickname: SrishtiParts (or any name you prefer)
   - Library Path: point to MyLibrary.kicad_sym in this repo
4. Preferences -> Manage Footprint Libraries
5. Global Libraries tab -> click "+" -> set:
   - Nickname: same as above
   - Library Path: point to the MyLibrary.pretty/ folder in this repo
6. Click OK on both - parts are now searchable in KiCad's symbol/footprint picker

## Verification notes

Each part's pinout is taken directly from the manufacturer's datasheet or
verified component data (e.g. cross-checked against EasyEDA's library entry
for the ESP32-DevKitC-VE). Footprint pad dimensions are measured where
possible; any estimated dimensions are flagged below. Always verify
footprint fit against a physical part before sending a board to fabrication.

### RYLR998
- Pinout confirmed from datasheet page 3 (pin description table)
- Pad pitch (2.54mm) confirmed from datasheet mechanical drawing
- Pad width/depth are reasonable estimates - verify against physical module
  before fab

### ESP32-DEVKITC-VE
- Pinout (38 pins) confirmed against EasyEDA's verified ESP32-DEVKITC-VE.1
  component
- Pin pitch (2.54mm) and row spacing (25.4mm / 1.0") confirmed by direct
  pad coordinate measurement in EasyEDA footprint editor
- Pad diameter (1.5mm) and drill size (0.8mm) are standard header-pin
  estimates - verify against physical board pin holes before fab

## Contributing

Feel free to open an issue or pull request if you spot an error in any part,
or want to contribute a new one.

## License

This library is released under CC-BY-SA 4.0 (see LICENSE) - free to use, modify,
and share, including commercially, as long as derivative libraries are shared
under the same license and original sources/authors are credited.
