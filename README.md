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
| **002** | *To be announced* | — | — | In Progress |
| **003** | *To be announced* | — | — | Upcoming |
| **004** | *To be announced* | — | — | Upcoming |
| **005** | *To be announced* | — | — | Upcoming |
| **006** | *To be announced* | — | — | Upcoming |
| **007** | *To be announced* | — | — | Upcoming |
| **008** | *To be announced* | — | — | Upcoming |
| **009** | *To be announced* | — | — | Upcoming |
| **010** | *To be announced* | — | — | Upcoming |

*(Days 011 through 100 will be populated daily as solutions are published.)*

---

## Project Log

### Day 1: [Office-to-PDF Auto-Viewer (`docx-to-pdf-viewer`)](https://github.com/aotlover9-base-eth/docx-to-pdf-viewer)
- **Problem**: Opening Word, PowerPoint, or Excel documents on Linux usually requires launching heavy office software or manually uploading files to Google Drive just to read them.
- **Solution**: A native desktop integration for Dolphin and GNOME Files. Clicking any document converts it to PDF in the background, shows a progress indicator, and opens it directly in Evince.
- **Key Features**:
  - SHA-256 caching layer for instant (<0.15s) re-opening.
  - Headless conversion via native or Flatpak LibreOffice.
  - Automatic XDG MIME type registration.

---

## Repository Links & Profile
- GitHub Profile: [@aotlover9-base-eth](https://github.com/aotlover9-base-eth)
