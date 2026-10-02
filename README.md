# 100 Days, 100 Problems, 100 Solutions (Vibe Coded)

A challenge to build 100 practical software utilities in 100 days. Each project tackles a specific real-world workflow bottleneck, missing feature, or technical annoyance.

---

## Challenge Rules

- **1 Real Problem Daily**: Focused on actual daily workflow friction, system limitations, and productivity blockers.
- **Fast, Practical Engineering**: Pair-programmed iteratively (Vibe Coded) to produce working, reliable software quickly.
- **Open Source & Documented**: Every project contains its own repository, clean source code, and a simple setup guide.
- **Minimal Dependencies**: Standalone utilities designed to run locally with minimal setup overhead.

---

## Challenge Tracker

| Day | Problem Description | Repository / Solution | Tech Stack | Status |
|:---:|:---|:---|:---|:---:|
| **001** | Opening `.docx`, `.pptx`, `.xlsx` on Linux without a full office suite or cloud uploads | [**docx-to-pdf-viewer**](https://github.com/aotlover9-base-eth/docx-to-pdf-viewer) | Python, Bash, LibreOffice Headless, Zenity, Evince, XDG | Completed |
| **002** | Accidentally leaking API keys, credentials, and PII in screenshots shared on X/GitHub | [**maskshot**](https://github.com/aotlover9-base-eth/maskshot) | Python 3.11+, Tesseract OCR, Pillow, Wayland/X11, Rich, Watchdog | Completed |
| **003** | Bluetooth headset profile downgrades (HFP mono), orphaned audio streams & missing per-app mixer | [**pipeswitch**](https://github.com/aotlover9-base-eth/pipeswitch) | Python 3.10+, GTK 4, Libadwaita, PipeWire Filter-Chain DSP, WirePlumber, Rich | Completed |
| **004** | *To be announced* | — | — | Upcoming |
| **005** | *To be announced* | — | — | Upcoming |

*(Days 006 through 100 will be populated daily as solutions are published.)*

---

## Project Log

### Day 1: [Office-to-PDF Auto-Viewer (`docx-to-pdf-viewer`)](https://github.com/aotlover9-base-eth/docx-to-pdf-viewer)
- **Problem**: Opening Word, PowerPoint, or Excel documents on Linux usually requires launching heavy office software or manually uploading files to Google Drive just to read them.
- **Solution**: A native desktop integration for Dolphin and GNOME Files. Clicking any document converts it to PDF in the background, shows a progress indicator, and opens it directly in Evince.
- **Key Features**:
  - SHA-256 caching layer for instant (<0.15s) re-opening.
  - Headless conversion via native or Flatpak LibreOffice.
  - Automatic XDG MIME type registration.

### Day 2: [Screenshot & Clipboard Secret Sanitizer (`maskshot`)](https://github.com/aotlover9-base-eth/maskshot)
- **Problem**: Sharing code screenshots, terminal error logs, or dashboard captures on X, GitHub, or Discord risks accidentally leaking live API keys (`sk-...`, `ghp_...`, `AKIA...`), database credentials, private IPs, or emails.
- **Solution**: A 100% offline, local CLI and clipboard utility that scans screenshots with Tesseract OCR, detects sensitive tokens and credentials, and redacts them in <300ms using blur, pixelation, or blackout masks.
- **Key Features**:
  - `maskshot clip`: Instantly sanitizes clipboard image with a single hotkey and updates clipboard with desktop notification.
  - `maskshot sanitize`: Redacts files with Gaussian Blur, Retro Pixelate, or Badge Blackout styles.
  - `maskshot watch`: Background daemon automatically sanitizing screenshot folders.
  - Zero cloud reliance: 100% local OCR & image processing, zero API fees, zero risk of data leaking to external servers.

### Day 3: [Linux Audio & Bluetooth Auto-Switcher, Per-App Mixer & DSP Effects (`pipeswitch`)](https://github.com/aotlover9-base-eth/pipeswitch)
- **Problem**: On Linux (PipeWire / PulseAudio), Bluetooth headphones often degrade to low-quality mono phone call mode (HFP), disconnecting devices leaves apps silently playing to dead/virtual sinks, and redirecting individual app audio or applying clean acoustic EQ requires complex terminal commands.
- **Solution**: A peak-interactive terminal user interface (TUI) with full mouse support and Rich CLI that automatically locks Bluetooth to A2DP high fidelity, provides per-app volume and dynamic output routing, includes a 6-band parametric EQ with acoustic presets, and offers 1-click sound diagnostic and rescue.
- **Key Features**:
  - **Auto-Switch & Codec Lock**: Real-time event daemon auto-switches to connected headsets and locks to high-fidelity stereo with desktop alerts.
  - **Per-App Mixer**: Real-time volume controls (up to 150% boost) and dynamic output destination routing per running application.
  - **DSP Audio Effects & 6-Band EQ**: Powered by PipeWire filter-chains with presets for Bass Boost, Vocal Clarity, Dynamic V-Curve, and 3D Virtual Spatializer.
  - **1-Click Audio Rescue**: Instant stream diagnostic, un-mute, and recovery for muted or stranded applications.
  - **Interactive Terminal Console**: Zero-bloat Textual TUI with full mouse clicking, sliders, tabs, and live PipeWire hardware sync.

---

## Repository Links & Profile
- GitHub Profile: [@aotlover9-base-eth](https://github.com/aotlover9-base-eth)
