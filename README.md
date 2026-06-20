# Srishti's KiCad Parts Library

Custom KiCad symbols and footprints for components missing from the official
KiCad libraries, built and verified while working on embedded systems / IoT
projects.

## Why this exists

Some parts (especially modules from smaller manufacturers like REYAX) aren't
available in KiCad's default libraries or on SnapEDA/EasyEDA. This repo
collects symbols and footprints I've built and verified against datasheets,
so they're reusable for future projects and for anyone else who needs them.

## Contents

| Part | Manufacturer | Package | Datasheet |
|---|---|---|---|
| RYLR998 | REYAX | 5-pin castellated SMD, 2.54mm pitch | [Datasheet](https://reyax.com/upload/products_download/download_file/RYLR998_EN.pdf) |

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

Each part's pinout is taken directly from the manufacturer's datasheet.
Footprint pad dimensions are measured from datasheet mechanical drawings
where available; any estimated dimensions are flagged in that part's section
below. Always verify footprint fit against a physical part before sending
a board to fabrication.

### RYLR998
- Pinout confirmed from datasheet page 3 (pin description table)
- Pad pitch (2.54mm) confirmed from datasheet mechanical drawing
- Pad width/depth are reasonable estimates - verify against physical module
  before fab

## Contributing

Feel free to open an issue or pull request if you spot an error in any part,
or want to contribute a new one.

## License

This library is released under CC-BY-SA 4.0 (see LICENSE) - free to use, modify,
and share, including commercially, as long as derivative libraries are shared
under the same license and original sources/authors are credited.
