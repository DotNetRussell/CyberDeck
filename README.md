# CyberDeck

CyberDeck is a terminal-based tool inspired by sci-fi interfaces (like those from *Alien* and hacker movies) for managing and executing penetration testing commands. It provides an interactive menu system to browse categorized commands, search for specific ones, and copy them to the clipboard. Built with Python and curses for a retro CRT feel, it's designed for penetration testers to quickly access common commands during engagements.

## Features

- **Sci-Fi Themed Interface**: Boot and shutdown sequences with animations for an immersive experience.
- **Command Database**: Categorized commands for passive mapping, vulnerability scanning, reverse shells, and more. Commands are fetched and updated from a remote JSON source.
- **Search Functionality**: Quickly search commands by name or description.
- **Clipboard Integration**: Copy commands directly to the clipboard (requires `pyperclip`).
- **Customizable Settings**: Change text color and toggle animations.
- **Fallback Mode**: If curses is unavailable, falls back to a command-line tool for converting file line endings (Unix, Windows, Mac).
- **Cross-Platform Support**: Commands tagged for Windows, Linux, or both (Win/Lin).
- **Error Logging**: Logs issues to `~/.cyberdeck/error.log`.

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/DotNetRussell/CyberDeck.git
   cd CyberDeck
   ```

2. Install dependencies (optional for clipboard and full functionality):
   ```
   pip install pyperclip requests
   ```
   - Note: The tool requires `curses` (built-in on Unix-like systems; on Windows, use Windows Subsystem for Linux or install via `pip install windows-curses`).

3. Run the tool:
   ```
   python3 cyberdeck.py
   ```

## Usage

- **Interactive Mode** (with curses):
  - Boot sequence initializes the interface.
  - Navigate menus using arrow keys, Enter to select, Esc to go back.
  - **Commands**: Browse categories and view command details (name, description, OS, and command string).
  - **Search**: Enter a query to filter commands.
  - **Settings**: Change text color or toggle animations.
  - **Shutdown**: Exit with a themed shutdown sequence.

- **Fallback Command-Line Mode** (without curses):
  - Converts line endings in files:
    ```
    python3 cyberdeck.py input_file output_file -f unix
    ```
    - Options: `unix`, `windows`, `mac`.

Commands are stored in `~/.cyberdeck/commands.json` and updated automatically from the remote source on startup if a newer version is available.

## Screenshots

[![Categories Menu](https://pbs.twimg.com/media/G178ZDLWAAAhGlW.png)](https://pbs.twimg.com/media/G178ZDLWAAAhGlW.png)
[![PowerShell Commands](https://pbs.twimg.com/media/G178bjIXIAAVZBe.png)](https://pbs.twimg.com/media/G178bjIXIAAVZBe.png)
[![Command Detail View](https://pbs.twimg.com/media/G178iGPWUAAyuZs.png)](https://pbs.twimg.com/media/G178iGPWUAAyuZs.png)

## Contributing

Feel free to submit pull requests for new commands, bug fixes, or features. Update the `commands.json` with new entries following the format:
- Name, Category (ID), Description, Command, OS ("Windows", "Linux", "Win/Lin").

## Latest Release

[Latest Release](https://github.com/DotNetRussell/CyberDeck/releases/latest)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
