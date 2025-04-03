<div align="center">
  <img src="logo.png" alt="AppBackup Vault Logo" width="200" height="200">
  <h1>AppBackup Vault</h1>
  <p>A lightweight, user-friendly desktop tool for backing up and restoring application settings on Windows 11</p>
  
  <p>
    <a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.8%2B-blue.svg" alt="Python 3.8+"></a>
    <a href="https://pypi.org/project/appbackup-vault/"><img src="https://img.shields.io/badge/pypi-v1.0.0-blue.svg" alt="PyPI Version"></a>
    <a href="https://github.com/mikl0s/appbackup-vault/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License"></a>
    <a href="https://github.com/mikl0s/appbackup-vault/actions"><img src="https://img.shields.io/badge/build-passing-brightgreen.svg" alt="Build Status"></a>
    <a href="https://github.com/mikl0s/appbackup-vault/issues"><img src="https://img.shields.io/github/issues/mikl0s/appbackup-vault.svg" alt="Issues"></a>
  </p>
  
  <p>
    <a href="#key-features">Features</a> •
    <a href="#installation">Installation</a> •
    <a href="#usage">Usage</a> •
    <a href="#screenshots">Screenshots</a> •
    <a href="#development">Development</a> •
    <a href="#license">License</a>
  </p>
</div>

## 🚀 Key Features

AppBackup Vault simplifies the process of backing up and restoring application-specific settings and data on Windows 11, without requiring full system backups.

- **Simple Installation**: Install with a single command via pip
- **Modern UI**: Clean, responsive interface with Tokyo Night-inspired dark theme
- **Dual-Pane Layout**: Intuitive selection of applications for backup and restore
- **Cloud Integration**: Easily set backup locations to Dropbox, OneDrive, or custom paths
- **Version Management**: Track and restore from multiple backup versions
- **Metadata & Notes**: Add notes to backups for future reference
- **Auto-Updates**: Stay current with built-in update checking

## 📦 Installation

AppBackup Vault requires Python 3.8 or higher, which can be installed from the [Microsoft Store](https://www.microsoft.com/en-us/p/python-38/9mssztt1n39l) or the [Python website](https://www.python.org/downloads/).

```bash
# Install from PyPI
pip install appbackup-vault

# Run the application
appbackup-vault
```

## 🔧 Usage

### Backing Up Applications

1. Launch AppBackup Vault by running `appbackup-vault` in your terminal or command prompt
2. Navigate to the **Backup** tab
3. From the left pane, select applications you want to back up
4. Click "Add Selected ->" to move them to the right pane
5. (Optional) Add notes about this backup in the text area at the bottom
6. Click "Backup Items in List" to start the backup process

### Restoring Applications

1. Navigate to the **Restore** tab
2. Browse the available backups in the left pane
3. Select the specific backup versions you want to restore
4. Click "Restore Items in List" to restore the selected versions

### Settings Configuration

1. Navigate to the **Settings** tab
2. Set your preferred backup location or use the "Detect Cloud Storage..." button
3. Toggle between Dark and Light themes (Dark is the default)
4. Check for application updates

## 📸 Screenshots

*Coming soon*

## 🛠️ Development

AppBackup Vault is built with:

- [Python 3.8+](https://www.python.org/)
- [DearPyGui](https://github.com/hoffstadt/DearPyGui) for the GUI
- [py7zr](https://github.com/miurahr/py7zr) for compression (future implementation)

### Project Structure

```
AppBackup Vault/
├── src/
│   └── appbackup_vault/
│       ├── __init__.py
│       ├── main.py        # Entry point
│       ├── gui.py         # UI setup and layout
│       └── utils.py       # Helpers (config handling, etc.)
├── docs/
│   ├── coding-guidelines.md
│   ├── project-prd.md
│   ├── project-prompt.md
│   ├── plan.md
│   └── ui.md
├── pyproject.toml
└── README.md
```

### Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/mikl0s/appbackup-vault.git
   cd appbackup-vault
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```

3. Install development dependencies:
   ```bash
   pip install -e ".[dev]"
   ```

4. Run the application in development mode:
   ```bash
   python -m appbackup_vault
   ```

### Coding Guidelines

- Follow [PEP 8](https://pep8.org/) style guidelines
- Keep files under 500 lines (split if necessary)
- Add docstrings to all modules, classes, and functions
- Use type hints where practical
- See [docs/coding-guidelines.md](docs/coding-guidelines.md) for complete details

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- [DearPyGui](https://github.com/hoffstadt/DearPyGui) for the amazing GUI framework
- [Tokyo Night Theme](https://github.com/enkia/tokyo-night-vscode-theme) for the color scheme inspiration

---

<div align="center">
  <sub>Built with ❤️ by <a href="https://github.com/mikl0s">Mikkel Georgsen</a></sub>
</div>