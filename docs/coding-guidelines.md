# Coding Guidelines for AppBackup Vault

## Project Overview
These guidelines govern the development of "AppBackup Vault," a Python-based desktop application using DearPyGui for managing app backups and restores on Windows 11. The tech stack includes Python 3.8+, DearPyGui for the GUI, and `py7zr` for 7zip compression (to be added later). The initial focus is on delivering a fully functional UI, with core functionality to follow.

## General Principles

### File Size Limit
- No project file (excluding external libraries or dependencies) may exceed 500 lines of code (excluding comments and blank lines).
- If a file exceeds 500 lines, refactor it by splitting into logical modules or functions in separate files (e.g., split `main.py` into `main.py` and `gui.py`).

### Documentation
- Keep code well-documented with:
  - Docstrings for all modules, classes, and functions explaining purpose, parameters, and return values.
  - Inline comments for complex logic or non-obvious decisions (e.g., UI layout choices).
- Aim for clarity so another developer can understand the code with minimal effort.

### Modularity
- Organize code into small, reusable modules with single responsibilities (e.g., one module for UI setup, another for future backup logic).
- Use Python packages (e.g., `src/appbackup_vault/`) to group related files.

### Readability
- Follow PEP 8 for style (e.g., 4-space indents, 79-character line limit).
- Use descriptive variable/function names (e.g., `create_app_list` instead of `make_list`).

## Tech Stack Specifics

### Python
- Use type hints where practical (e.g., `def show_gui(window: int) -> None:`).
- Leverage standard libraries (e.g., `os`, `pathlib`) for file operations.

### DearPyGui
- Define UI components in a dedicated module (e.g., `gui.py`) if `main.py` grows large.
- Use DearPyGui’s layout tools (e.g., tabs, groups) to keep the interface clean and responsive.
- Keep theme definitions concise and modular (e.g., in a `themes.py` file if >50 lines).

### Future Libraries (py7zr)
- Encapsulate 7zip operations in a utility module (e.g., `backup_utils.py`) when implemented, keeping it under 500 lines.

## Project-Specific Rules

### File Structure
- Example layout:
  AppBackup Vault/
  ├── src/
  │   ├── __init__.py
  │   ├── main.py        # Entry point, <500 lines
  │   ├── gui.py         # UI setup and layout
  │   └── utils.py       # Helpers (e.g., config handling, to be added)
  ├── pyproject.toml     # Package config
  └── README.md
- Split files if any exceed 500 lines (e.g., move large GUI sections to `gui_apps.py` or `gui_restore.py`).

### UI Development
- Focus on UI first: Use placeholder data (e.g., dummy app lists) and non-functional buttons that update a status bar.
- Implement light/dark themes (dark default) in a way that’s easy to maintain (e.g., separate theme functions).

### Version Control
- Use Git for version control.
- After completing a task:
  - Run `git add .` to stage changes.
  - Run `git commit -m "Descriptive message (e.g., 'Add initial UI with tabs and theme toggle')"` to commit.
  - Do **not** push to a remote repository—keep changes local.

## Task Tracking
- If working from a project plan, mark tasks/stories/phases as complete using:
  - [ ] for incomplete, [x] for complete, OR
  - Green checkmark (✅) next to the task/phase title.
- Follow the plan’s layout (e.g., if it’s a list, update the list; if it’s sections, update within sections).
- Example:
  - [x] Design UI layout with tabs
  - [ ] Implement app scanning logic
  OR
  - ✅ Design UI layout with tabs
  - Implement app scanning logic

## Best Practices

### Error Handling
- Add basic error handling in the UI (e.g., catch DearPyGui setup errors) with user-friendly messages.
- Log errors to a status bar or console for now (e.g., `dpg.set_value("status", "Error occurred")`).

### Development Workflow
- Start with a minimal `main.py` (<500 lines) that launches the GUI.
- Split into additional files (e.g., `gui.py`) as features grow, ensuring no file exceeds 500 lines.

## Enforcement
- Use a linter (e.g., `flake8`) to enforce PEP 8 and check line counts manually or via a script.
- Refactor any file exceeding 500 lines before marking a task complete (e.g., split `main.py` into `main.py` and `gui.py`).