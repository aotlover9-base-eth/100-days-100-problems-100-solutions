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
| **006** | Zombie dev servers auto-restarting, TIME_WAIT socket locks, and hidden docker-proxy collisions | [**portdock**](https://github.com/aotlover9-base-eth/portdock) | Python 3.10+, Rich TUI, psutil, Linux /proc, POSIX Signals | Completed |
| **007** | Strict portal upload limits (<2MB), crooked mobile camera scans, and multi-doc recipe merges | [**pdfchop**](https://github.com/aotlover9-base-eth/pdfchop) | Python 3.10+, PyMuPDF, OpenCV, Pillow, ReportLab, Rich TUI | Completed |
| **008** | Rigid calendar bloat, missing 24-hr day allocation awareness, and all-or-nothing reminder alarms | [**hyperchunk**](https://github.com/aotlover9-base-eth/hyperchunk) | Kotlin, Jetpack Compose, Material 3, Android SDK 35, AppWidgetProvider | Completed |
| **009** | *To be announced* | — | — | Upcoming |

*(Days 009 through 100 will be populated daily as solutions are published.)*

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
### Day 6: [Interactive Port Conflict Resolver & Ghost Process Dissector (`portdock`)](https://github.com/aotlover9-base-eth/portdock)
- **Problem**: Developers frequently hit `EADDRINUSE` port collision errors when restarting dev servers. Standard commands like `lsof -i :PORT | kill` only terminate the child worker, prompting dev supervisors (`nodemon`, `vite`, `npm run dev`, `cargo watch`) to instantly restart on the same port, or leave orphaned ghost processes and hidden Docker containers (`docker-proxy`) occupying ports invisibly.
- **Solution**: A high-performance terminal utility and full-screen Rich TUI dashboard engineered to inspect, diagnose, and resolve port collisions in milliseconds with supervisor hierarchy traversal, Docker container detection, and kernel socket release verification.
- **Key Features**:
  - **Sub-50ms Socket Kill**: Graceful `SIGTERM` with 200ms escalation to `SIGKILL` and kernel socket release verification loop.
  - **Ghost Process Dissector (`-t, --tree`)**: Climbs the process hierarchy to terminate root supervisors and all child workers in one sweep.
  - **Full Interactive TUI Dashboard**: Real-time terminal UI with memory RSS, CPU %, uptime, bind scopes (`LOCAL` vs `PUBLIC`), and quick-kill shortcuts (`k`, `t`, `d`).
  - **Deep Port Inspector (`portdock <port>`)**: Inspects any port, displaying bind scope, process metadata, supervisor hierarchy, and visual worker process trees.
  - **Docker Mapping Detection**: Identifies whether a port is held by a Docker container (`docker-proxy`) and displays container name and image.
  - **Scriptable Automation**: Includes `portdock wait <port>` and `portdock list --json` for CI/CD and deployment healthchecks.

### Day 7: [Overkilled Offline PDF Swiss-Army Workstation (`pdfchop`)](https://github.com/aotlover9-base-eth/pdfchop)
- **Problem**: Submission portals, job applications, and college forms enforce strict file size limits (<2MB or <500KB), while camera photos of documents have uneven shadows and crooked angles. Free online tools (iLovePDF, SmallPDF) upload private documents to third-party cloud servers, watermark files, or enforce daily limits.
- **Solution**: A 100% offline, local PDF workstation with an interactive zero-flicker TUI featuring live 24-bit Truecolor Unicode half-block page previews, adaptive target-size byte compression, OpenCV auto-deskew, and page recipe stitching.
- **Key Features**:
  - **Smart Target-Size Compressor**: Exact byte budget guarantees (`pdfchop compress file.pdf --max 2MB`) with multi-stage adaptive downsampling and binary-search quantization.
  - **Live Half-Block TUI Preview**: Renders real-time visual page thumbnails at 60fps directly in the terminal window without opening external viewers.
  - **OpenCV Scan Rescuer**: Auto-deskew angle correction and illumination estimation to flatten mobile camera shadows and binarize pages.
  - **Recipe Stitcher & TOC**: Merges documents with page slices (`doc1.pdf:1-5 doc2.pdf:10-15`) and auto-generates unified PDF bookmarks outline.
  - **Security & Privacy Studio**: AES-256 encryption, password unlocking, and comprehensive metadata/XMP sanitization.

### Day 8: [HyperOS 3 Native 24-Hour Day Planner & Homescreen Widget (`hyperchunk`)](https://github.com/aotlover9-base-eth/hyperchunk)
- **Problem**: Setting up a structured daily routine in traditional calendar apps (Google Calendar, Notion) requires creating 15 disconnected events with tedious date pickers, while failing to provide an instant visual overview of how your full 24-hour day is divided across sleep, routines, deep work, lectures, and rest.
- **Solution**: A minimal, 100% native Kotlin Android application built specifically with Xiaomi HyperOS 3 design aesthetics (ultra-rounded 32dp squircles, frosted glass panels, buttery spring physics, and zero boxy rectangles). Features an interactive clock wheel drum picker, selective exact alarms, and a native homescreen widget.
- **Key Features**:
  - **24-Hour Time-Chunking System**: Divide 00:00 to 24:00 into intuitive focus blocks with auto-duration formatting and overlap awareness.
  - **HyperOS 3 Design Language**: Custom squircle surfaces, velvet dark canvas, pill badges, and fluid spring animations throughout all sheets, tabs, and modals.
  - **Interactive Clock Wheel Picker**: Smooth vertical drum scroll for hours (`00-23`) and minutes (`00-59`) with haptic snapping and center magnification.
  - **Selective Exact Alarms**: Per-task alarm toggling—ring sound & vibration for college lectures, hydration, or gym, while keeping rest periods completely silent.
  - **Native Homescreen Widget**: HyperOS 3 rounded card with live active task title, countdown timer ("45m left"), real-time progress bar, and up-next preview.
  - **Day-of-Week Presets**: Independent routines for Monday through Sunday with 1-tap day schedule duplication.
  - **24-Hour Visual Ribbon**: Live proportional color gauge tracking day allocation with a real-time moving indicator needle.

---

## Repository Links & Profile
- GitHub Profile: [@aotlover9-base-eth](https://github.com/aotlover9-base-eth)
