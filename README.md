# CyberDeck

CyberDeck is a Python application designed as a portable, searchable reference tool for cybersecurity professionals. It organizes common hacking commands into intuitive categories, making it easy to browse, view details, and copy snippets to your clipboard. The goal is to create the ultimate "pocketbook" companion for red teamers, pentesters, and bug bounty hunters—always ready for on-the-go reference.

Key highlights:
- **Retro Aesthetic**: Green-on-black teletype UI for that cyberpunk vibe.
- **Offline-First**: No internet required; all commands are local.
- **Expandable Design**: Simple structure for adding new commands and categories.

[Latest Release](https://github.com/DotNetRussell/CyberDeck/releases/latest)

[![Categories Menu](https://pbs.twimg.com/media/G178ZDLWAAAhGlW.png)](https://pbs.twimg.com/media/G178ZDLWAAAhGlW.png)
[![PowerShell Commands](https://pbs.twimg.com/media/G178bjIXIAAVZBe.png)](https://pbs.twimg.com/media/G178bjIXIAAVZBe.png)
[![Command Detail View](https://pbs.twimg.com/media/G178iGPWUAAyuZs.png)](https://pbs.twimg.com/media/G178iGPWUAAyuZs.png)

A retro-styled terminal-based "pocketbook" for hackers, featuring a curated collection of 136+ useful penetration testing and security research commands. Built with a teletype-inspired Text User Interface (TUI) for quick reference during engagements.

## Overview



Watch a quick demo of the interface in action: [Video Demo](https://x.com/DotNetRussell/status/1972385080904761732).

## Features

- **Categorized Navigation**: Commands grouped into practical sections, including:
  - Passive Mapping
  - Web App Testing Mapping
  - Vuln Scanning
  - Subdomain Scanning
  - Initial Access Scanning
  - Post Exploitation
  - Reverse Shells
  - LDAP TTY Shell
  - Cracking
  - Misc Linux
  - PowerShell
  - Mimikatz
  - Misc Windows

- **Search Functionality**: Quickly find commands across all categories using keywords.

- **Command Details**: View full syntax, descriptions, and examples for each entry.

- **Clipboard Integration**: Press `C` to copy the selected command directly to your clipboard.

- **Keyboard-Driven**: 
  - Arrow keys: Navigate menus and lists.
  - Enter: Select category or command.
  - Esc: Go back to previous menu.
  - `C`: Copy command (in detail view).

- **Cross-Platform**: Runs on Linux, macOS, and Windows (with appropriate Python setup).

## Installation

CyberDeck is a lightweight Python app. Ensure you have Python 3.8+ installed.

1. Clone the repository:
   ```
   git clone https://github.com/DotNetRussell/CyberDeck.git
   cd CyberDeck
   ```

2. Install dependencies (uses standard libraries like `rich` for the TUI):
   ```
   pip install -r requirements.txt
   ```
   *Note: If no `requirements.txt` exists yet, manually install `rich` via `pip install rich`.*

3. Launch the app:
   ```
   python cyberdeck.py  # Replace with the main script name if different
   ```

## Usage

1. Run the app to open the main menu.
2. Use arrow keys to highlight a category (e.g., "PowerShell") and press Enter.
3. Browse the list of commands in that category.
4. Select a command with Enter to view its details, including syntax and description.
5. Press `C` to copy the command to your clipboard, or any other key to return.
6. Use the search feature (accessible via a dedicated menu or hotkey) to query across all commands.

Example workflow:
- Navigate to "PowerShell" category.
- Select "Get Local Users on Windows".
- View: `Get-LocalUser | Select Name, Enabled, Description`.
- Copy and paste into your terminal.

For adding commands: Edit the underlying data file (likely a JSON or YAML structure) and submit a pull request.

## Roadmap

- Full-text search improvements.
- Export to PDF/Markdown.
- Mobile-friendly export or companion app.
- Integration with common tools (e.g., auto-execute in a sandbox).

This is still in early development—feedback welcome!

## Contributing

Contributions are encouraged! Here's how to get started:

1. Fork the repo and create a feature branch (`git checkout -b feature/amazing-feature`).
2. Commit your changes (`git commit -m 'Add amazing feature'`).
3. Push to the branch (`git push origin feature/amazing-feature`).
4. Open a Pull Request.

To add new commands:
- Locate the commands data file (e.g., `commands.json`).
- Follow the schema: `{ "category": "PowerShell", "name": "Get Local Users", "command": "Get-LocalUser", "description": "..." }`.
- Test in the app and submit.

Please discuss major changes via issues first.

## License

Distributed under the MIT License. See `LICENSE` for more details (or add one if missing).

## Acknowledgments

- Built with love by [@DotNetRussell](https://x.com/DotNetRussell).
- Inspired by classic cyberpunk tools and the need for a hacker's quick-reference deck.

---

⭐ Star the repo if you find it useful! Questions? Open an issue.
=======
>>>>>>> Stashed changes
