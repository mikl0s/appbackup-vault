Prompt for AI Coder:

I need you to develop a Python-based desktop application named "AppBackup Vault" using DearPyGui that is installable and runnable with a single command (e.g., `pip install appbackup-vault && appbackup-vault`), with the following specifications. The solution should be a Python package distributed via PyPI, requiring no manual compilation—just standard Python script execution. Prioritize building a fully functional UI first, with placeholder elements, before implementing the core functionality.

1. Distribution and Setup:
   - Package the application as a Python module uploadable to PyPI, installable with `pip install appbackup-vault`.
   - Define a command-line entry point (e.g., `appbackup-vault`) in `setup.py` or `pyproject.toml` for immediate execution post-install.
   - Include all dependencies (e.g., DearPyGui, py7zr for 7zip) in the package configuration, installed automatically via pip.

2. Auto-Updating:
   - Implement an auto-update feature that checks PyPI for newer versions on startup (e.g., using `pip index versions appbackup-vault` or a version API).
   - Prompt the user in the GUI to update with a single command (e.g., `pip install --upgrade appbackup-vault`), ideally automating the process with a button click (UI placeholder for now).

3. Core Functionality (UI First):
   - When run (e.g., `appbackup-vault`), launch a DearPyGui-based GUI application titled "AppBackup Vault".
   - Display a placeholder list of installed applications on Windows 11, including:
     - Name of each application (e.g., "App1", "App2").
     - Approximate size (e.g., "50 MB").
     - Drive where installed (e.g., "C:").
     - Total sizes per drive and a grand total (e.g., "C: 80 MB, Total: 80 MB").
     - Last backup date (e.g., "2025-04-01" or "Never").

4. Backup Functionality (UI First):
   - Allow users to set a backup location via the GUI, stored in a `.appbackupvault` file in the user’s home folder (e.g., `C:\Users\<Username>\`) by default, with a custom location option.
   - In the settings, include buttons labeled "Dropbox" and "OneDrive" that set the backup location to the local filesystem paths of these apps (e.g., `C:\Users\<Username>\Dropbox` or `C:\Users\<Username>\OneDrive`), if they exist, for user convenience. Syncing is handled by Dropbox/OneDrive desktop apps, not the program itself.
   - Enable selection of one or more apps via checkboxes in the UI (placeholder for now).
   - Placeholder button: “Backup Selected” to simulate backup action.

5. Restore Functionality (UI First):
   - Add a "Restore" section in the GUI showing placeholder backup versions for each app (e.g., a list or dropdown with "Backup 2025-04-02").
   - Provide two placeholder buttons:
     - "Restore Over Existing" (simulates overwrite).
     - "Backup Current & Restore" (simulates dual action).
   - Display placeholder metadata (e.g., size, date) for each backup version.

6. Backup Notes & Metadata (UI First):
   - Include a text input field in the GUI for user-added notes per backup (placeholder text for now).
   - Plan to create JSON files (e.g., `notepad-20250402-190431.json`) with metadata (timestamp, size, app name, source paths) alongside .7z backups (UI placeholder only).

7. GUI Design:
   - Design a modern-looking GUI using DearPyGui with a clean, responsive layout.
   - Include:
     - App list with selection options, sizes, drives, and backup dates (placeholder data).
     - Settings section with backup location input and "Dropbox"/"OneDrive" buttons.
     - Restore section with version selection and action buttons.
     - Notes input field per backup.
     - Progress feedback area (e.g., “Status: Ready” or “Backup clicked”).
     - Light/dark themes with dark as the default, including a toggle to switch between them.
   - Focus on completing the UI first—use dummy data and non-functional buttons that update a status bar for now.

8. Development Features (UI First):
   - Support cached scan data: Plan to save app scan results to `appscan.json` in the home folder, with a rescan button (placeholder in UI).

9. Technical Requirements:
   - Ensure compatibility with Windows 11 and Python 3.8+.
   - Use DearPyGui for the GUI and `py7zr` for future 7zip compression—all as pip dependencies.
   - Handle UI edge cases (e.g., layout responsiveness) within Python.

10. Deliverables:
    - A PyPI package installable via `pip install appbackup-vault`.
    - Source code with comments on key UI components (e.g., layout, theme setup).
    - A README with:
      - Install/run instructions (e.g., `pip install appbackup-vault && appbackup-vault`).
      - Update instructions (e.g., `pip install --upgrade appbackup-vault`).
      - Notes on UI development status.

11. Key Emphasis:
    - Installable/runnable with one command, assuming Python is present.
    - Deliver a fully functional UI first using DearPyGui, with placeholder elements, before adding core functionality (scanning, backups, restores).
    - Modern, user-friendly GUI with light/dark themes (dark default).
    - No compilation—just Python and pip.

Please ensure the solution prioritizes a polished, interactive UI that launches and looks great on first run. Use placeholder data and non-functional buttons for now—focus on the look and feel. Functionality (scanning, backups, etc.) will be added later. Let me know if you need clarification!