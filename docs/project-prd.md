# Product Requirements Document (PRD)

## Product Name
AppBackup Vault

## Version
1.0

## Date
April 02, 2025

## Overview

### Purpose
AppBackup Vault is a lightweight, user-friendly desktop tool designed to simplify the backup and restoration of application-specific user settings and data on Windows 11. It targets tech-savvy users, IT professionals, and gamers who need a portable, efficient solution to preserve app configurations without full system backups, using a local filesystem approach.

### Goals
- Provide a single-command installable Python application via PyPI.
- Offer a modern, themeable desktop GUI using DearPyGui for managing app backups and restores.
- Enable seamless auto-updates and a robust UI foundation, with functionality to follow.
- Ensure portability and ease of use with no manual compilation required.

### Target Audience
- Windows 11 users needing to migrate or safeguard app settings.
- Developers seeking a flexible, iterable tool for app data management.

## Features

### 1. Installation & Distribution
- Requirement: Installable and runnable with a single command (e.g., `pip install appbackup-vault && appbackup-vault`).
- Details: Distributed as a Python package on PyPI, with all dependencies (DearPyGui, py7zr, etc.) auto-installed via pip.
- Success Criteria: Users can install and launch the app in one terminal command, assuming Python 3.8+ is present.

### 2. Auto-Updating
- Requirement: Automatically check for updates and prompt the user to upgrade.
- Details: On startup, query PyPI for newer versions and offer a one-click update via `pip install --upgrade appbackup-vault` (UI placeholder for now).
- Success Criteria: Update prompt appears in the GUI when a new version is available (to be implemented after UI).

### 3. App Scanning & Display (UI First)
- Requirement: List all installed Windows 11 applications with relevant details in the GUI.
- Details: Display placeholder app name, size (MB/GB), drive location, total sizes per drive, and grand total across drives. Show last backup date if applicable (dummy data initially).
- Success Criteria: GUI shows a clean, accurate-looking app list on launch.

### 4. Backup Functionality (UI First)
- Requirement: Back up selected apps’ user data into 7zip files stored on the local filesystem, with UI setup first.
- Details: 
  - User sets a backup location (stored in `.appbackupvault` in home folder, customizable).
  - In the settings GUI, include "Dropbox" and "OneDrive" buttons that set the backup location to local paths (e.g., `C:\Users\<Username>\Dropbox` or `C:\Users\<Username>\OneDrive`), if present, for convenience. No direct syncing integration—syncing is handled by Dropbox/OneDrive desktop apps.
  - Placeholder selection of apps and “Backup Selected” button in the GUI.
- Success Criteria: GUI allows setting a backup path and simulates backup action with status feedback.

### 5. Restore Functionality (UI First)
- Requirement: Restore app settings from backups with version management, with UI setup first.
- Details: 
  - Show placeholder backup versions per app in a “Restore” GUI section (e.g., list or dropdown).
  - Offer two placeholder buttons: “Restore Over Existing” and “Backup Current & Restore”.
- Success Criteria: GUI displays backup options and simulates restore actions with status updates.

### 6. Backup Notes & Metadata (UI First)
- Requirement: Store notes and metadata with each backup, with UI setup first.
- Details: 
  - Include a placeholder text input for notes in the GUI.
  - Plan for `<appname>-<timestamp>.json` files alongside .7z files with metadata (timestamp, size, app name, source paths).
- Success Criteria: GUI includes a notes field that feels functional.

### 7. User Interface
- Requirement: Provide a modern, themeable desktop GUI.
- Details: 
  - Use DearPyGui for a clean, responsive design.
  - Include app list, backup controls, settings with location input and "Dropbox"/"OneDrive" buttons, restore section, notes input, and status feedback.
  - Support light/dark themes (dark default) with a toggle.
- Success Criteria: GUI is visually appealing, responsive, and theme switch works instantly on first launch.

### 8. Development Features (UI First)
- Requirement: Support rapid iteration during development.
- Details: 
  - Plan to cache app scans in `appscan.json` (home folder, configurable), with a rescan button in the GUI (placeholder for now).
- Success Criteria: GUI includes a rescan option that updates status (to be implemented later).

## Technical Requirements

### Platform
- Windows 11

### Tech Stack
- Language: Python 3.8+
- GUI Framework: DearPyGui
- Compression: py7zr (7zip, for later implementation)
- System Access: `winreg`, `psutil`, or `wmi` for app scanning (for later implementation)
- Dependencies: Managed via pip, included in PyPI package

### Performance
- GUI loads in <2 seconds on a standard Windows 11 system.
- Memory usage stays below 200 MB during UI operation.

### Constraints
- No manual compilation; pure Python execution.
- Files must not exceed 500 lines (refactor/split if larger).
- Python must be pre-installed by the user.
- Focus on UI completion first, with functionality (scanning, backups, restores) to follow.

## Deliverables
1. PyPI Package: `appbackup-vault`, installable via `pip install appbackup-vault`.
2. Source Code: Well-commented, split into modules (e.g., `main.py`, `gui.py` for UI).
3. Documentation: README with install, run, update, and UI status notes.

## Non-Functional Requirements
- Usability: Intuitive GUI with minimal learning curve.
- Maintainability: Modular code, <500 lines per file, clear comments.

## Assumptions
- Users have Python 3.8+ installed (available via Microsoft Store).
- Windows 11 permissions allow GUI operation.

## Risks
- Risk: GUI layout may feel cluttered with many elements.  
  Mitigation: Use tabs or collapsible sections for clarity.

## Success Metrics
- GUI launches and is fully navigable on first run.
- Theme toggle works instantly.
- Positive initial feedback on UI design and usability.