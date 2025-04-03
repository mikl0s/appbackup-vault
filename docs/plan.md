# AppBackup Vault - Project Plan

This document outlines the development plan for AppBackup Vault, prioritizing UI development as per the project prompt and PRD. Tasks should be marked complete using `[x]` or `✅`.

## Phase 1: Project Setup & Initial Structure

*   [ ] Initialize Git repository locally (`git init`).
*   [ ] Create initial project directory structure:
    ```
    AppBackup Vault/
    ├── src/
    │   └── appbackup_vault/
    │       ├── __init__.py
    │       └── main.py
    ├── docs/
    │   ├── coding-guidelines.md
    │   ├── project-prd.md
    │   ├── project-prompt.md
    │   ├── plan.md  # This file
    │   └── ui.md    # To be created
    ├── pyproject.toml
    └── README.md
    ```
*   [ ] Configure `pyproject.toml` with basic package metadata (name, version, author) and initial dependencies (`dearpygui`).
*   [ ] Define command-line entry point (`appbackup-vault`) in `pyproject.toml`.
*   [ ] Create initial `README.md` with project title and brief description.
*   [ ] Create basic `src/appbackup_vault/main.py` with placeholder function to launch DearPyGui window.

## Phase 2: Core UI Development (Placeholders & Mock Data)

*   [ ] Implement main DearPyGui window structure in `src/appbackup_vault/gui.py` (refactor from `main.py` if needed to keep under 500 lines).
*   [ ] Add main tab bar with sections: "Backup", "Restore", "Settings", "About".
*   [ ] **Backup Tab UI:**
    *   [ ] Implement scrollable table for application list using `dpg.add_table`.
    *   [ ] Define table columns: Checkbox (for selection), Name, Size, Drive, Last Backup. Populate with placeholder data (at least 10-15 diverse entries).
    *   [ ] Add display area below the table for "Total for C:", "Total for D:", "Grand Total:", populated with calculated placeholder totals.
    *   [ ] Add "Backup Selected" button (non-functional, updates status bar).
    *   [ ] Add multi-line text input for "Backup Notes" (placeholder).
    *   [ ] Add "Rescan" button (non-functional, updates status bar).
*   [ ] **Restore Tab UI:**
    *   [ ] Add dropdown/list to select an application (populated with placeholders).
    *   [ ] Add table/list to display placeholder backup versions for the selected app (Timestamp, Size, Notes preview).
    *   [ ] Add "Restore Over Existing" button (non-functional, updates status bar).
    *   [ ] Add "Backup Current & Restore" button (non-functional, updates status bar).
*   [ ] **Settings Tab UI:**
    *   [ ] Add input field for "Backup Location" with a default placeholder path.
    *   [ ] Add "Browse..." button next to location input (non-functional).
    *   [ ] Add "Set to Dropbox" button (non-functional, updates status bar/location field).
    *   [ ] Add "Set to OneDrive" button (non-functional, updates status bar/location field).
    *   [ ] Implement theme toggle (e.g., checkbox or button) switching between light and dark themes. Ensure dark theme is the default.
    *   [ ] Add "Check for Updates" button (non-functional, updates status bar).
    *   [ ] Add status text area for update check results (e.g., "Click button to check for updates").
*   [ ] **About Tab UI:**
    *   [ ] Add text displaying Application Name ("AppBackup Vault") and Version (e.g., "1.0.0-dev").
    *   [ ] Add placeholder text for links or license info.
*   [ ] Implement a persistent status bar at the bottom of the main window.
*   [ ] Ensure UI elements are arranged logically, responsive to window resizing, and visually appealing based on mockups.
*   [ ] Ensure all UI code is well-commented, especially layout decisions.
*   [ ] Refactor UI code into separate files (e.g., `gui_backup_tab.py`) if `gui.py` exceeds 500 lines.

## Phase 3: Configuration & Basic Logic (Placeholders)

*   [ ] Create `src/appbackup_vault/config.py` module.
*   [ ] Implement placeholder function to load/save backup location from/to `.appbackupvault` in the user's home directory. Connect this to the Settings UI input field.
*   [ ] Implement placeholder logic for "Set to Dropbox"/"Set to OneDrive" buttons: check for common paths (e.g., `%USERPROFILE%\Dropbox`, `%USERPROFILE%\OneDrive`) and update the location field if found.
*   [ ] Implement basic logic for app selection checkboxes in the Backup tab table (track selected items).
*   [ ] Connect all placeholder buttons ("Backup Selected", "Restore", "Rescan", "Check for Updates") to update the status bar with appropriate messages (e.g., "Backup action triggered.", "Restore action triggered.", "Rescan triggered.", "Checking for updates...").
*   [ ] Ensure configuration logic stays within file size limits.

## Phase 4: Core Functionality Implementation (Post-UI)

*   *This phase involves implementing the actual backend logic and is planned after the UI is complete and approved.*
*   [ ] Implement Windows application scanning logic (using `winreg`, `psutil`, or `wmi`) to populate the app list accurately.
*   [ ] Implement app scan caching to `appscan.json` and connect "Rescan" button functionality.
*   [ ] Implement backup process using `py7zr`:
    *   [ ] Identify relevant user data/settings paths for selected apps (requires research/configuration).
    *   [ ] Compress selected data to `.7z` files in the configured backup location.
    *   [ ] Generate corresponding `.json` metadata files (timestamp, size, app name, source paths, notes).
    *   [ ] Update "Last Backup" date in the UI.
*   [ ] Implement restore process:
    *   [ ] List available backups based on `.json` files in the backup location.
    *   [ ] Implement "Restore Over Existing" logic (extract `.7z`).
    *   [ ] Implement "Backup Current & Restore" logic (perform backup first, then restore).
*   [ ] Implement auto-update check logic:
    *   [ ] Query PyPI for the latest version on startup.
    *   [ ] Display update prompt in the GUI if a newer version exists.
    *   [ ] (Optional Stretch Goal) Implement automated update execution via `pip install --upgrade appbackup-vault`.
*   [ ] Implement robust error handling for file operations, scanning, backup, and restore.

## Phase 5: Packaging & Distribution

*   [ ] Finalize all dependencies (e.g., `py7zr`, `requests` for update check) in `pyproject.toml`.
*   [ ] Ensure entry point `appbackup-vault` works correctly.
*   [ ] Update `README.md` with comprehensive installation (`pip install appbackup-vault`), execution (`appbackup-vault`), and update (`pip install --upgrade appbackup-vault`) instructions. Add notes on current development status (UI complete, functionality pending).
*   [ ] Build the package using `python -m build`.
*   [ ] Perform local installation test: `pip install dist/appbackup_vault-*.whl`.
*   [ ] Test running the application via the installed command: `appbackup-vault`.
*   [ ] (Optional) Prepare for and upload the package to PyPI.

## Ongoing Tasks

*   [ ] Adhere strictly to `docs/coding-guidelines.md` (PEP 8, 500 lines/file limit, documentation, modularity).
*   [ ] Regularly refactor code to maintain structure and readability as features are added.
*   [ ] Commit changes locally using Git with descriptive messages after completing logical units of work (`git add .`, `git commit -m "..."`).