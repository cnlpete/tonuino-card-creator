# Tonuino Card Creator

**Tonuino Card Creator** is a lightweight, zero-dependency, single-file web application for creating, customizing, and printing RFID card covers and labels for the [TonuINO](https://www.tonuino.de/) DIY audio player system.

It automatically formats card covers for standard A4 sticker sheet grids—specifically optimized for **Hama 5028 / Herma 5028** printable labels (83.8 × 50.8 mm, 10 labels per A4 page)—and includes live print calibration offsets, automated online album art fetching, and interactive crop & layout tools.

---

## Features

- **Targeted Grid Print Engine**: Pre-calibrated for 10-label A4 sheets (83.8 × 50.8 mm per card, 2 columns × 5 rows).
- **Automated Artwork Search**: Integrated cover search via iTunes Search API and MusicBrainz Cover Art Archive.
- **Flexible Formatting Modes**:
  - **Cover + Panel (Split)**: Full square cover on the left with title/artist detail panel on the right.
  - **Fill / Crop**: Full-card artwork expansion with touch & mouse drag-to-pan positioning.
  - **Ambient Blur**: Centered square cover with blurred background fill.
  - **Letterbox**: Clean centered square cover display.
- **Text Overlay Toggle**: Option to show or hide title & artist text overlays across all styles.
- **Print Calibration**: Adjustable Top and Left margin offsets in millimeters to account for printer tray variations.
- **Data Safety & Automatic Migration**:
  - Automatically detects and migrates legacy data keys from previous project versions.
  - LocalStorage persistence (no server required, 100% privacy-friendly).
  - Backup & restore via JSON file export/import and clipboard manager.
- **Print-Ready CSS**: Clean print stylesheets hiding UI controls and forcing exact A4 page dimensions and background colors.

---

## Quick Start

Because **Tonuino Card Creator** is a self-contained single-page web app, no build step or node environment is required.

1. Download or clone this repository.
2. Open `index.html` directly in any modern desktop web browser (Chrome, Firefox, Safari, Edge).
3. Search or upload album artwork, customize your layout, place cards into sheet slots (1–10), and hit **Print Sheet** (`Ctrl+P` / `Cmd+P`).

---

## Recommended Print Settings

To ensure exact physical dimensions when printing onto label sheets:

| Setting | Value |
| :--- | :--- |
| **Paper Size** | A4 |
| **Orientation** | Portrait |
| **Margins** | **None** (or 0 mm / Custom 0) |
| **Scale** | **100%** (Do NOT use "Fit to Printable Area") |
| **Background Graphics** | **Enabled / Checked** |

> **Tip**: Print a test page on plain paper first and overlay it with your sticker sheet over a light source to verify alignment. Adjust the **Top** and **Left** calibration offsets in the toolbar if necessary.

---

## Repository Structure

```text
.
├── index.html       # Standalone application code (HTML, Tailwind CDN, JS)
├── README.md        # Project documentation
├── INSTALL.md       # Self-hosting and installation instructions
└── LICENSE          # GNU General Public License v3.0
```

---

## Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to check the issues page or submit a pull request.

---

## License

Distributed under the **GNU General Public License v3.0** (GPL-3.0). See [`LICENSE`](LICENSE) for details.