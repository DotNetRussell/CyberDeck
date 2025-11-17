# CyberDeck

**CyberDeck** is a **terminal-based penetration testing command dictionary and cookbook** with a **sci-fi CRT aesthetic** inspired by *Alien*, *Blade Runner*, and classic hacker films. Built in Python using `curses`, it delivers an immersive, retro-futuristic interface for browsing, searching, and copying commands for execution 

Whether you're on a red team engagement, CTF, or just need quick access to common tools, CyberDeck keeps your workflow fast, organized, and *visually epic*.

---

## Features

| Feature | Description |
|-------|-----------|
| **Sci-Fi Themed UI** | Boot/shutdown sequences with typewriter animations, CRT-style text, and Weyland-Yutani branding. |
| **Dynamic Command Database** | Commands pulled from remote `commands.json`, auto-updated on launch (configurable). |
| **Categorized Commands** | Organized by phase: Recon, Scanning, Exploitation, Post-Exploitation, Reverse Shells, etc. |
| **Full-Text Search** | Dual-panel search across **commands** and **cookbook recipes**. |
| **Clipboard Integration** | Press `C` to copy any command instantly (`pyperclip` required). |
| **Cookbook Recipes** | Step-by-step multi-command playbooks (e.g., "Lateral Movement via WMI"). |
| **Related Commands** | Context-aware suggestions with live navigation. |
| **Customizable Appearance** | Choose from 8 retro color schemes: `toxic green`, `yellow`, `cyan`, etc. |
| **Animation Toggle** | Disable boot/typewriter effects for speed. |
| **Cross-Platform Tags** | Commands labeled: `Windows`, `Linux`, or `Win/Lin`. |
| **Fallback CLI Mode** | If `curses` fails (e.g., Windows without WSL), use as a **line-ending converter**. |
| **Error Logging** | All issues logged to `~/.cyberdeck/error.log`. |

---

## Screenshots


[![Categories Menu](https://i.imgur.com/8YNGYKD.png)
[![Categories Menu](https://i.imgur.com/gfCzgfs.png)
[![Categories Menu](https://i.imgur.com/tzEbcmk.png)
[![Categories Menu](https://i.imgur.com/kj1IoQU.png)
[![Categories Menu](https://i.imgur.com/pBM6LDY.png)
[![Categories Menu](https://i.imgur.com/WfQWeAI.png)
[![Categories Menu](https://i.imgur.com/LD8FTz6.png)
[![Categories Menu](https://i.imgur.com/DH5PMjM.png)
[![Categories Menu](https://i.imgur.com/HbImOcc.png)

---

## Installation

### 1. Clone the Repo
```bash
git clone https://github.com/DotNetRussell/CyberDeck.git
cd CyberDeck
```

### 2. Install Dependencies (Recommended)
```bash
pip install pyperclip requests
```

> **Note**:  
> - `curses` is built-in on **Linux/macOS**.  
> - On **Windows**, use **WSL** or install:  
>   ```bash
>   pip install windows-curses
>   ```

### 3. Run CyberDeck
```bash
python3 cyberdeck.py
```

> First run creates `~/.cyberdeck/` and downloads latest `commands.json`.

---

## Usage

### Interactive Mode (`curses`)

| Action | Keys |
|------|------|
| Navigate | `↑` `↓` |
| Select | `Enter` |
| Go Back | `Esc` |
| Copy Command | `C` |
| Search | `Search` → type query |
| Switch Panel (Search) | `←` `→` |

#### Menu Options
- **Commands** → Browse by category → View details
- **Search** → Find commands/recipes instantly
- **Cookbook** → Run multi-step playbooks
- **Settings** → Change color, toggle animations, force update
- **Shutdown** → Exit with style

---

### Fallback CLI Mode (No `curses`)

Convert line endings:
```bash
python3 cyberdeck.py input.txt output.txt -f unix
```

Options:
- `-f unix` → `\n` (LF)
- `-f windows` → `\r\n` (CRLF)
- `-f mac` → `\r` (CR)

---

## Data & Updates

- **Commands**: Stored in `~/.cyberdeck/commands.json`
- **Recipes**: Stored in `~/.cyberdeck/recipes/*.json`
- **Auto-Update**: Enabled by default on startup
- **Force Update**: Press `F` in Settings

> All data synced from:  
> [https://github.com/DotNetRussell/CyberDeck](https://github.com/DotNetRussell/CyberDeck)

---

## Cookbook Recipes

Create your own in `~/.cyberdeck/recipes/`:

```json
{
	"name": "Attack Path Visualization with BloodHound",
	"description": "Load collected data into BloodHound to reveal privilege escalation routes.",
	"tools": [
		{
			"name": "BloodHound",
			"description": "AD relationship graphing tool",
			"url": "https://github.com/BloodHoundAD/BloodHound"
		}
	],
	"steps": [
		{
			"index": 1,
			"name": "Start Services",
			"command": "neo4j start; bloodhound",
			"description": "Launch database and GUI."
		},
		{
			"index": 2,
			"name": "Import Dataset",
			"command": "Drag domain_data.zip into BloodHound interface",
			"description": "Load harvested JSON files."
		},
		{
			"index": 3,
			"name": "Pathfinding Queries",
			"command": "Run: Shortest Paths from Owned to Domain Admins",
			"description": "Identify viable attack chains."
		}
	]
}
```

---

## Contributing

We welcome contributions! Help grow the command library and recipes.

### How to Contribute
1. Fork the repo
2. Add new entries to `commands.json` or create `.json` recipes
3. Submit a Pull Request

#### Command Format
```json
{
      "Name": "Mimikatz - DCSync Administrator Hash",
      "Category": 16,
      "Description": "Mimikatz: Perform DCSync to retrieve Administrator account hash from DC",
      "Command": "lsadump::dcsync /user:corp\\Administrator",
      "OS": "Windows",
      "id": 1,
      "related": [
        0,
        2,
        13,
        15,
        16
      ]
}
```

---

## Latest Release

[Download Latest](https://github.com/DotNetRussell/CyberDeck/releases/latest)

---

## License

[MIT License](LICENSE) – Free to use, modify, and distribute.

---

> **"In space, no one can hear you `nc -lvnp 4444`"**  
> — *CyberDeck, probably*

---

**Built with** `Python` **·** **Maintained by** [@DotNetRussell](https://x.com/DotNetRussell)

