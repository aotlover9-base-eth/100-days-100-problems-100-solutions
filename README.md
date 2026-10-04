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
| **003** | Bluetooth headset profile downgrades (HFP mono), orphaned audio streams & missing per-app mixer | [**pipeswitch**](https://github.com/aotlover9-base-eth/pipeswitch) | Python 3.10+, Textual TUI, PipeWire Filter-Chain DSP, WirePlumber, Rich | Completed |
| **004** | Sharing clipboard, tokens, files, or photos between Linux and phone on local WiFi without cloud leaks | [**clipshare**](https://github.com/aotlover9-base-eth/clipshare) | Python 3.10+, qrcode, Rich, HTTP Threading Server, HTML5/CSS Mobile Web | Completed |
| **005** | Downloading videos, audio, image galleries, and text from social posts without ad spam or compression | [**omniget**](https://github.com/aotlover9-base-eth/omniget) | Python 3.10+, Textual TUI, yt-dlp, ffmpeg, Rich | Completed |
| **006** | *To be announced* | — | — | Upcoming |

*(Days 007 through 100 will be populated daily as solutions are published.)*

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

### Day 4: [Local LAN P2P Clipboard & File Share via QR Code (`clipshare`)](https://github.com/aotlover9-base-eth/clipshare)
- **Problem**: Transferring code snippets, API keys, passwords, or files between a Linux terminal and a smartphone usually requires messaging yourself on WhatsApp/Telegram/Discord (exposing private tokens to cloud platforms) or setting up bulky tools.
- **Solution**: A 1-command micro-utility that discovers local WiFi LAN IP, serves clipboard contents or files over an ephemeral local HTTP server, and renders a scannable ASCII QR code directly in the terminal.
- **Key Features**:
  - **Terminal ASCII QR Code**: Instant high-contrast half-block QR code scannable directly with smartphone cameras.
  - **Multi-Source Ingestion**: Shares Wayland/X11 clipboard, files, auto-compressed directories, piped stdin, or text strings.
  - **Obsidian Dark Mobile Web UI**: Responsive mobile receiver with 1-tap copy to phone clipboard and file previews.
  - **Bi-Directional Dropzone**: Upload photos or files from phone camera directly into `~/Downloads/clipshare/` on the PC.
  - **Ephemeral & Auto-Shutdown**: Automatic server termination after transfer or 120s timeout. Zero cloud servers.

### Day 5: [Universal Social Post & Media Downloader TUI (`omniget`)](https://github.com/aotlover9-base-eth/omniget)
- **Problem**: Downloading content from social media platforms (YouTube, X, Instagram, Reddit, Facebook) is filled with adware-ridden websites, popups, aggressive video compression, stripped captions, broken audio tracks, and messy disorganized file clutter.
- **Solution**: A peak-interactive terminal user interface (Rich TUI) and CLI that auto-detects platforms, organizes downloads into dedicated platform subfolders, uses clean sequential bundle naming, and downloads best-quality video (up to 4K), audio (HQ MP3), photo galleries, and post captions 100% locally.
- **Key Features**:
  - **Platform-Dedicated Folders**: Zero clutter — downloads route automatically into separate subfolders (`x/`, `youtube/`, `reddit/`, `instagram/`, `facebook/`).
  - **Clean Sequential Naming**: Folders and ZIP archives are cleanly formatted (`tweet 1.zip`, `tweet 2.zip`, `youtube 1.zip`, etc.) instead of messy 200-character social media titles.
  - **Bundle Everything (.zip) Archive**: 1-click downloads video, extracted audio MP3, uncompressed gallery photos, caption (`.md` & `.txt`), and `metadata.json` into a single organized ZIP archive.
  - **Video Quality Resolution Picker**: Choose exact video quality (1080p Full HD, 720p HD, 480p, 360p, or best available) via interactive prompt or CLI flag (`-q / --quality`).
  - **Uncompressed Photo Galleries**: Upgrades Twitter images to `name=orig` and YouTube thumbnails to `maxresdefault.jpg` without artificial image caps.
  - **Multi-Tier Robust Fallbacks**: Integrated FxTwitter and Reddit API fallbacks ensure image, video, and text posts download without failure.
  - **Peak Interactive Terminal TUI**: Clipboard auto-detection, live byte download telemetry, speed (MB/s), ETA, and post inspection cards.
  - **100% Local & Free**: Powered by native `yt-dlp` and `ffmpeg`. Zero cloud relays, zero API subscriptions, zero tracking.

---

## Repository Links & Profile
- GitHub Profile: [@aotlover9-base-eth](https://github.com/aotlover9-base-eth)
