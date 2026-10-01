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
| **003** | *To be announced* | — | — | Upcoming |
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

---

## Repository Links & Profile
- GitHub Profile: [@aotlover9-base-eth](https://github.com/aotlover9-base-eth)
