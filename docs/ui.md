# AppBackup Vault - UI Design Specification

This document details the user interface (UI) design for AppBackup Vault, built using DearPyGui. The design prioritizes clarity, ease of use, and the ability to handle potentially large lists of applications, based on the project requirements and provided mockups.

## 1. Main Window

*   **Title:** "AppBackup Vault"
*   **Layout:** A primary window containing a tab bar for navigation between main sections.
*   **Theme:** Defaults to a custom Dark theme inspired by the "Tokyo Night" color scheme. This theme will feature dark blue/purple hues as primary background colors. Key interactive elements, selected items, or distinct panes (like the dual panes in Backup/Restore) may use slightly brighter but still subtle background variations to create a sense of depth or "elevation". A standard Light theme will also be available. A toggle switch in the Settings tab will allow instant switching between the Dark (default) and Light themes.
*   **Status Bar:** A persistent status bar at the bottom of the window will display application status messages (e.g., "Ready", "Backup started...", "Update available", error messages).

## 2. Tab Structure

The main window will feature the following tabs:

1.  **Backup:** Primary view for selecting applications and initiating backups.
2.  **Restore:** View for selecting and restoring previous backups.
3.  **Settings:** Configuration options, including backup location and theme.
4.  **About:** Application information and links.

## 3. Backup Tab

This tab utilizes a dual-pane layout for clear selection management, inspired by Mockup 2.

*   **Layout:** Divided horizontally or vertically into two main panes.
    *   **Left Pane: Available Applications**
        *   **(Optional) Filter:** Text input "Filter Apps:" for searching the list below.
        *   **List/Table:** Scrollable table (`dpg.add_table`) displaying *all* detected installed applications.
            *   Columns: `Name`, `Size`, `Drive`, `Last Backup`.
            *   Selection: Clicking a row selects it. Multiple selections possible (e.g., using Ctrl/Shift clicks). Selected rows are visually highlighted. Apps already added to the right pane might be greyed out or marked.
            *   Buttons: "Rescan Applications" (updates this list, placeholder action), "Add Selected ->" (moves selected apps from this pane to the right pane).
        *   **Summary (Optional):** Display totals for *all* listed applications (Grand Total, Total per Drive).
    *   **Right Pane: Selected for Backup**
        *   **List/Table:** Scrollable table (`dpg.add_table`) displaying applications chosen for the *next* backup operation.
            *   Columns: `Name`, `Estimated Size` (same as Size from left), `Last Backup`.
            *   Selection: Clicking a row selects it for removal.
        *   Buttons: "<- Remove Selected" (removes selected apps from this list, making them available again in the left pane).
        *   **Summary:** Display totals for *only* the applications in this list (Total Selected Size).
*   **Bottom Section (Below Panes):**
    *   **Backup Notes:** Multi-line text input labeled "Backup Notes:" (applies to the entire backup job).
    *   **Primary Action:** "Backup Items in List" button (prominently placed, placeholder action: updates status bar based on the right pane's content).

## 4. Restore Tab

This tab uses a dual-pane layout for selecting specific backup versions to restore.

*   **Layout:** Divided horizontally or vertically into two main panes.
    *   **Left Pane: Available Backups**
        *   **List/Tree:** A scrollable list or tree view (`dpg.add_listbox` or `dpg.add_tree_node`) showing applications that have backups available in the configured backup location.
        *   Expanding an application node reveals its available backup versions (listed by `Timestamp`, potentially showing `Size`).
        *   Selection: Clicking a specific backup version selects it. Multiple selections possible.
    *   **Right Pane: Selected for Restore**
        *   **List/Table:** Scrollable table (`dpg.add_table`) displaying the specific application backup versions selected for the restore operation.
            *   Columns: `Application Name`, `Backup Timestamp`, `Size`.
        *   Selection: Clicking a row selects it for removal.
        *   Buttons: "<- Remove Selected" (removes selected versions from this list).
*   **Bottom Section (Below Panes):**
    *   **Action Buttons:**
        *   "Restore Items in List" (placeholder action: updates status bar).
        *   "Backup Current & Restore Items in List" (placeholder action: updates status bar).

## 5. Settings Tab

*   **Layout:** Organized into logical groups.
    *   **Backup Target Location Group:**
        *   Text label: "Backup Target Directory:"
        *   A text input field displaying the current backup target path (editable or read-only with browse button).
        *   "Browse..." button (opens a folder selection dialog, placeholder action).
        *   "Detect Cloud Storage..." button (placeholder action: simulates scanning for local Dropbox/OneDrive paths via registry/config files and potentially offers them as options to set the target directory, updates status bar).
        *   *Note:* When a target directory is set/confirmed, the application should check if an expected structure (e.g., `AppBackup Vault` subfolder or a `.appbackupvault_config` file) exists. If not, it should prompt the user (placeholder dialog/status message): "Initialize target directory 'path/to/target' for AppBackup Vault?"
    *   **Appearance Group:**
        *   Text label: "Theme:"
        *   A checkbox or switch labeled "Use Dark Theme" (toggles between light/dark themes). Default is checked (Dark).
    *   **Updates Group:**
        *   "Check for Updates" button (placeholder action: updates status bar).
        *   A read-only text area below the button to display update status.

## 6. About Tab

*   **Layout:** Simple text display.
    *   Application Title: "AppBackup Vault"
    *   Version: "Version X.Y.Z" (placeholder, e.g., "1.0.0-dev")
    *   Placeholder text for acknowledgments, license information, or links to a project website/repository.

## 7. Placeholder Interactions

*   All action buttons ("Backup Selected", "Restore", "Rescan", "Check for Updates", "Browse", "Set to...") will initially be non-functional but will update the main window's status bar with a message indicating the action was triggered (e.g., "Status: Backup Selected button clicked.").
*   The application list, backup list, and summary totals will use static, hardcoded placeholder data.
*   The theme toggle will be functional, switching DearPyGui's theme.