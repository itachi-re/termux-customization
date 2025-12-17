<div align="center">

# 🚀 Termux Customization Guide

### Transform Your Android Terminal Into a Powerhouse! ⚡

[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-red.svg)](https://github.com/itachi-re/termux-customization)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/itachi-re/termux-customization/pulls)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/itachi-re/termux-customization/graphs/commit-activity)

<img src="https://raw.githubusercontent.com/termux/termux-app/master/art/termux-banner.svg" width="500" alt="Termux Banner">

**A complete, step-by-step guide to create the ultimate Termux experience**  
*Beautiful • Powerful • Productive*

[🎯 Quick Start](#-quick-start) • [📚 Full Guide](#-table-of-contents) • [🎨 Screenshots](#-screenshots) • [🤝 Contributing](#-contributing)

</div>

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎨 Beautiful Interface
- ✅ Modern Fish shell with auto-suggestions
- ✅ Eye-catching Fastfetch system info
- ✅ Gorgeous color schemes & themes
- ✅ Customizable Starship prompt
- ✅ Nerd Fonts support

</td>
<td width="50%">

### ⚡ Enhanced Productivity
- ✅ Modern CLI tools (bat, exa, ripgrep)
- ✅ Smart aliases & functions
- ✅ Directory jumping with Z
- ✅ Fuzzy finding with FZF
- ✅ One-command setup script

</td>
</tr>
</table>

---

## 🎯 Quick Start

Get your perfect Termux setup in just **3 commands**:

```bash
# 1️⃣ Clone this repository
pkg install git -y && git clone https://github.com/itachi-re/termux-customization.git

# 2️⃣ Navigate to the directory
cd termux-customization

# 3️⃣ Run the magic setup script
bash setup.sh
```

> **⚠️ Important:** Restart Termux after installation!

---

## 📱 Before You Start

### Prerequisites Checklist

- [ ] 📲 Android 5.0 or higher
- [ ] 📦 Termux installed from [F-Droid](https://f-droid.org/en/packages/com.termux/) (NOT Play Store!)
- [ ] 🌐 Stable internet connection
- [ ] ⏱️ 10-15 minutes of your time

### Why F-Droid?

The Play Store version is **outdated** and **unmaintained**. Always use F-Droid for the latest features and security updates!

---

## 📚 Table of Contents

### 📖 Complete Guide

| Chapter | Topic | What You'll Learn |
|---------|-------|-------------------|
| 1️⃣ | [Introduction](#chapter-1-introduction) | Overview & prerequisites |
| 2️⃣ | [Initial Setup](#chapter-2-initial-setup--prerequisites) | Package management & storage |
| 3️⃣ | [Fish Shell](#chapter-3-fish-shell-installation--configuration) | Modern shell configuration |
| 4️⃣ | [Fastfetch](#chapter-4-fastfetch-setup--customization) | System info display |
| 5️⃣ | [Terminal Styling](#chapter-5-terminal-styling--themes) | Colors, fonts & themes |
| 6️⃣ | [Essential Tools](#chapter-6-essential-tools--utilities) | CLI utilities & packages |
| 7️⃣ | [Productivity](#chapter-7-productivity-enhancements) | Aliases, functions & shortcuts |
| 8️⃣ | [Advanced](#chapter-8-advanced-customizations) | Custom scripts & automation |
| 9️⃣ | [Backup & Restore](#chapter-9-backup--restore) | Save your configuration |
| 🔟 | [Troubleshooting](#chapter-10-troubleshooting) | Fix common issues |

---

## 🎨 Screenshots

<div align="center">

### Before 😐
```
$ ls
file1.txt  file2.txt  folder1
```

### After 🤩
```fish
➜ ~/projects 
❯ ls
📄 file1.txt  📄 file2.txt  📁 folder1
✨ Completed in 2ms
```

</div>

---

## Chapter 1: Introduction

### 🌟 What is Termux?

Termux is a **powerful terminal emulator** and **Linux environment** for Android that works **without root access**. It's like having a full Linux distribution in your pocket!

### 🎯 What You'll Achieve

By the end of this guide, you'll have:

- 🐚 **Fish Shell** - Smart autocompletion and syntax highlighting
- 🖼️ **Fastfetch** - Beautiful system information display
- 🎨 **Custom Themes** - Personalized color schemes
- ⚡ **Modern Tools** - Faster, better alternatives to classic commands
- 🚀 **Productivity Boost** - Aliases, shortcuts, and automation

### 📋 What You Need to Know

```
Basic Terminal Knowledge:
├── 📝 How to type commands
├── 📂 Basic file navigation (cd, ls)
├── ✏️ Text editing (nano/vim basics)
└── 📦 Package installation concepts
```

Don't worry if you're a beginner - we'll guide you through everything! 🤝

---

## Chapter 2: Initial Setup & Prerequisites

### 🎯 Step 1: Install Termux

<details>
<summary>📲 Click to expand installation instructions</summary>

1. Open **F-Droid** on your Android device
2. Search for **"Termux"**
3. Download and install
4. Open Termux

**Download Link:** [F-Droid Termux Page](https://f-droid.org/en/packages/com.termux/)

</details>

### 🔓 Step 2: Grant Storage Permission

Allow Termux to access your device files:

```bash
termux-setup-storage
```

📱 **Tap "Allow"** when the permission dialog appears.

This creates a `~/storage` directory with shortcuts to:
- 📥 Downloads
- 📸 DCIM (Camera)
- 🎵 Music
- 📄 Documents

### 🔄 Step 3: Update Package Lists

```bash
pkg update && pkg upgrade -y
```

<details>
<summary>⏱️ What's happening here?</summary>

- `pkg update` - Refreshes the list of available packages
- `pkg upgrade` - Upgrades all installed packages to latest versions
- `-y` - Automatically answers "yes" to all prompts

⏰ First run might take 3-5 minutes depending on your connection.

</details>

### 📦 Step 4: Install Essential Tools

```bash
pkg install -y git curl wget nano vim
```

| Tool | Purpose |
|------|---------|
| 🗂️ **git** | Version control & cloning repositories |
| 🌐 **curl** | Download files from the internet |
| 📡 **wget** | Alternative download tool |
| ✏️ **nano** | User-friendly text editor |
| ⚙️ **vim** | Powerful text editor |

### 🌍 Step 5: Change Repository Mirror (Optional)

For **faster downloads**, select a nearby mirror:

```bash
termux-change-repo
```

Use volume keys to navigate, select a mirror close to your location.

### 🎉 Checkpoint!

Test if everything works:

```bash
git --version
curl --version
```

If you see version numbers, you're good to go! ✅

> 💡 **Pro Tip:** If you encounter any errors, run `pkg update` again and retry.

**📚 Resources:**
- 📖 [Termux Wiki](https://wiki.termux.com/)
- 📘 [Official Documentation](https://termux.dev/)
- 🎥 [Termux YouTube Tutorials](https://www.youtube.com/results?search_query=termux+tutorial)

---

## Chapter 3: Fish Shell Installation & Configuration

### 🐟 What is Fish Shell?

**Fish** (Friendly Interactive Shell) is a smart and user-friendly command line shell with:

- 🎯 **Autosuggestions** - Predicts commands as you type
- 🌈 **Syntax Highlighting** - Colors commands for better readability
- 📝 **Tab Completions** - Intelligent command completion
- 🚀 **Modern Scripting** - Clean and readable syntax

### 🔧 Installation Process

#### Step 1: Install Fish

```bash
pkg install -y fish
```

#### Step 2: Set Fish as Default Shell

```bash
chsh -s fish
```

🔄 **Restart Termux** for changes to take effect.

#### Step 3: Configure Fish

Create the configuration directory:

```bash
mkdir -p ~/.config/fish
```

Create your main config file:

```bash
nano ~/.config/fish/config.fish
```

📝 **Copy and paste this basic configuration:**

```fish
# ═══════════════════════════════════════
# 🐟 FISH SHELL CONFIGURATION
# ═══════════════════════════════════════

# ─────────────────────────────────────
# 🎨 APPEARANCE
# ─────────────────────────────────────

# Disable the welcome message
set fish_greeting

# Set beautiful colors
set -g fish_color_command green
set -g fish_color_param cyan
set -g fish_color_error red --bold
set -g fish_color_quote yellow
set -g fish_color_redirection blue
set -g fish_color_end magenta
set -g fish_color_comment brblack

# ─────────────────────────────────────
# 📦 ALIASES - Quick Commands
# ─────────────────────────────────────

# 📂 Directory Navigation
alias ..='cd ..'
alias ...='cd ../..'
alias ....='cd ../../..'
alias ~='cd ~'
alias h='cd ~'

# 📋 File Listing
alias ll='ls -alh'
alias la='ls -A'
alias l='ls -CF'

# 🧹 System Commands
alias cls='clear'
alias q='exit'
alias c='clear'

# 🔄 Package Management
alias update='pkg update && pkg upgrade'
alias install='pkg install'
alias uninstall='pkg uninstall'
alias search='pkg search'

# 🗑️ Safety Aliases
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# 🔍 Quick Search
alias grep='grep --color=auto'
alias fgrep='fgrep --color=auto'
alias egrep='egrep --color=auto'

# ─────────────────────────────────────
# 🚀 ENVIRONMENT VARIABLES
# ─────────────────────────────────────

# Set default editor
set -gx EDITOR nano

# Add custom scripts to PATH
set -gx PATH $HOME/scripts $PATH
```

💾 Save with `Ctrl+X`, then `Y`, then `Enter`.

### 🎣 Step 4: Install Fisher Plugin Manager

Fisher manages Fish plugins. Install with one command:

```bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
```

### 🎨 Step 5: Install Essential Fish Plugins

```bash
# ✨ Auto-close brackets and quotes
fisher install jorgebucaran/autopair.fish

# 🚀 Jump to frequently used directories
fisher install jethrokuan/z

# 🎨 Colorful man pages
fisher install decors/fish-colored-man

# 📝 Better command history
fisher install jorgebucaran/fish-bax
```

<details>
<summary>📚 What each plugin does</summary>

- **autopair.fish** - Automatically closes `()`, `[]`, `{}`, `""`, `''`
- **z** - Jump to frequently visited directories with just `z dirname`
- **fish-colored-man** - Makes man pages colorful and easier to read
- **fish-bax** - Run bash scripts in Fish shell seamlessly

</details>

### 🌟 Step 6: Install Starship Prompt (Recommended)

Starship is a **blazing-fast**, **customizable** prompt that shows:
- 📂 Current directory
- 🌿 Git branch and status
- 🔋 Battery status
- ⏱️ Command execution time
- 🐍 Programming language versions

```bash
pkg install -y starship
```

Add to your `~/.config/fish/config.fish`:

```fish
# ─────────────────────────────────────
# ⭐ STARSHIP PROMPT
# ─────────────────────────────────────
starship init fish | source
```

Reload your config:

```bash
source ~/.config/fish/config.fish
```

### ✅ Test Your Setup

Type a command and see the magic:

```fish
# Start typing 'git' and see suggestions
git

# Try the z plugin (after visiting some directories)
cd ~/downloads
cd ~
z down  # Jumps to downloads!
```

### 🎨 Bonus: Custom Fish Functions

Create a handy update function:

```bash
nano ~/.config/fish/functions/sysupdate.fish
```

```fish
function sysupdate --description 'Update everything'
    echo "🔄 Updating Termux packages..."
    pkg update && pkg upgrade -y
    
    echo "🎣 Updating Fisher plugins..."
    fisher update
    
    echo "✨ All done!"
end
```

Now you can just type `sysupdate` to update everything!

**📚 Resources:**
- 🐟 [Fish Shell Documentation](https://fishshell.com/docs/current/)
- 🎣 [Fisher Plugin Manager](https://github.com/jorgebucaran/fisher)
- ⭐ [Starship Prompt](https://starship.rs/)
- 🎨 [Awesome Fish Plugins](https://github.com/jorgebucaran/awsm.fish)

---

## Chapter 4: Fastfetch Setup & Customization

### 🖼️ What is Fastfetch?

Fastfetch displays your **system information** in a beautiful format when you open your terminal. It's like neofetch but **faster** and more **customizable**!

Shows:
- 🤖 OS & Device info
- 💻 CPU & Memory
- 🔋 Battery status
- 🎨 Color palette
- ⏱️ Uptime

### 📥 Step 1: Install Fastfetch

```bash
pkg install -y fastfetch
```

### 🎯 Step 2: Test Default Configuration

```bash
fastfetch
```

You should see something like:

```
        🤖 Android
        ━━━━━━━━━━━━━━
        OS: Android 13
        Host: Samsung Galaxy
        Kernel: 5.10.43
        Uptime: 2 hours, 34 mins
        Shell: fish 3.6.1
        Terminal: Termux
        CPU: Snapdragon 888
        Memory: 3.2 GB / 8 GB
```

### 🎨 Step 3: Create Custom Configuration

Create the config directory:

```bash
mkdir -p ~/.config/fastfetch
```

Create your custom config:

```bash
nano ~/.config/fastfetch/config.jsonc
```

📝 **Here's an awesome configuration:**

```jsonc
{
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    
    "logo": {
        "source": "android",
        "padding": {
            "top": 1,
            "left": 3
        },
        "color": {
            "1": "green",
            "2": "green"
        }
    },
    
    "display": {
        "separator": "  ",
        "color": {
            "separator": "green",
            "keys": "cyan",
            "title": "green"
        }
    },
    
    "modules": [
        {
            "type": "title",
            "format": "┌─── {user-name}@{host-name} ───┐"
        },
        "break",
        {
            "type": "os",
            "key": " OS",
            "keyColor": "green"
        },
        {
            "type": "host",
            "key": "󰇄 Device",
            "keyColor": "blue"
        },
        {
            "type": "kernel",
            "key": " Kernel",
            "keyColor": "yellow"
        },
        {
            "type": "uptime",
            "key": "󰔟 Uptime",
            "keyColor": "magenta"
        },
        "break",
        {
            "type": "packages",
            "key": "󰏖 Packages",
            "keyColor": "cyan"
        },
        {
            "type": "shell",
            "key": " Shell",
            "keyColor": "green"
        },
        {
            "type": "terminal",
            "key": " Terminal",
            "keyColor": "blue"
        },
        "break",
        {
            "type": "cpu",
            "key": "󰘚 CPU",
            "keyColor": "red"
        },
        {
            "type": "memory",
            "key": " RAM",
            "keyColor": "yellow"
        },
        {
            "type": "disk",
            "key": "󰋊 Disk",
            "keyColor": "magenta"
        },
        {
            "type": "battery",
            "key": "󰁹 Battery",
            "keyColor": "green"
        },
        "break",
        {
            "type": "locale",
            "key": "󰗊 Locale",
            "keyColor": "cyan"
        },
        "break",
        {
            "type": "colors",
            "symbol": "circle"
        }
    ]
}
```

### 🚀 Step 4: Auto-run on Startup

Add to your `~/.config/fish/config.fish`:

```fish
# ─────────────────────────────────────
# 🖼️ FASTFETCH - System Info Display
# ─────────────────────────────────────
if status is-interactive
    fastfetch
    echo "" # Add spacing
end
```

Reload config:

```fish
source ~/.config/fish/config.fish
```

### 🎭 Step 5: Alternative ASCII Art

Want a different logo? Here are some options:

<details>
<summary>🐧 Linux Penguin</summary>

```bash
nano ~/.config/fastfetch/config.jsonc
```

Change logo section to:

```jsonc
"logo": {
    "source": "linux"
}
```

</details>

<details>
<summary>🎨 Custom ASCII Art</summary>

Create your own ASCII art:

```bash
nano ~/.config/fastfetch/custom-logo.txt
```

Add your ASCII art, then in config:

```jsonc
"logo": {
    "source": "~/.config/fastfetch/custom-logo.txt",
    "type": "file"
}
```

</details>

### 🎨 Color Schemes

Try different color schemes:

```jsonc
// 🔴 Red Theme
"color": { "1": "red", "2": "red" }

// 💙 Blue Theme
"color": { "1": "blue", "2": "cyan" }

// 💜 Purple Theme
"color": { "1": "magenta", "2": "blue" }

// 🌈 Rainbow Theme
"color": { "1": "rainbow", "2": "rainbow" }
```

### ⚡ Pro Tips

```bash
# Show fastfetch help
fastfetch --help

# List all available logos
fastfetch --list-logos

# Test without saving
fastfetch --config /path/to/test-config.jsonc

# Show only specific modules
fastfetch --structure "OS:Host:Kernel:Shell"
```

**📚 Resources:**
- 🖼️ [Fastfetch GitHub](https://github.com/fastfetch-cli/fastfetch)
- 📖 [Configuration Wiki](https://github.com/fastfetch-cli/fastfetch/wiki)
- 🎨 [ASCII Art Generator](https://www.asciiart.eu/)
- 💡 [Community Configs](https://github.com/fastfetch-cli/fastfetch/discussions/categories/config-showcase)

---

## Chapter 5: Terminal Styling & Themes

### 🎨 Make Your Terminal Beautiful!

Transform your terminal from boring to breathtaking with custom colors, fonts, and themes!

### 🎯 Method 1: Quick Styling (Easiest)

#### Install Termux Styling Package

```bash
pkg install -y termux-styling
```

#### Run the Style Selector

```bash
termux-style
```

📱 **How to use:**
- Use **Volume Up/Down** to navigate
- Press **Enter** to select
- Choose from **colors** and **fonts**

Popular choices:
- 🌃 **Dracula** - Dark purple theme
- 🌙 **Monokai** - Classic dark theme
- 🌊 **Nord** - Blue-ish cool theme
- 🔥 **Gruvbox** - Warm retro theme

### 🎨 Method 2: Manual Color Configuration

#### Step 1: Create Termux Directory

```bash
mkdir -p ~/.termux
```

#### Step 2: Choose Your Theme

<details>
<summary>🧛 Dracula Theme (Recommended)</summary>

```bash
nano ~/.termux/colors.properties
```

```properties
# ═══════════════════════════════════════
# 🧛 DRACULA THEME
# ═══════════════════════════════════════

background=#282a36
foreground=#f8f8f2
cursor=#f8f8f2

# Black + Dark Gray
color0=#000000
color8=#4d4d4d

# Red + Light Red
color1=#ff5555
color9=#ff6e67

# Green + Light Green
color2=#50fa7b
color10=#5af78e

# Yellow + Light Yellow
color3=#f1fa8c
color11=#f4f99d

# Blue + Light Blue
color4=#bd93f9
color12=#caa9fa

# Magenta + Light Magenta
color5=#ff79c6
color13=#ff92d0

# Cyan + Light Cyan
color6=#8be9fd
color14=#9aedfe

# Light Gray + White
color7=#bfbfbf
color15=#e6e6e6
```

</details>

<details>
<summary>🌲 Nord Theme</summary>

```properties
# ═══════════════════════════════════════
# 🌲 NORD THEME
# ═══════════════════════════════════════

background=#2e3440
foreground=#d8dee9
cursor=#d8dee9

color0=#3b4252
color1=#bf616a
color2=#a3be8c
color3=#ebcb8b
color4=#81a1c1
color5=#b48ead
color6=#88c0d0
color7=#e5e9f0

color8=#4c566a
color9=#bf616a
color10=#a3be8c
color11=#ebcb8b
color12=#81a1c1
color13=#b48ead
color14=#8fbcbb
color15=#eceff4
```

</details>

<details>
<summary>🔥 Gruvbox Dark</summary>

```properties
# ═══════════════════════════════════════
# 🔥 GRUVBOX DARK
# ═══════════════════════════════════════

background=#282828
foreground=#ebdbb2
cursor=#ebdbb2

color0=#282828
color1=#cc241d
color2=#98971a
color3=#d79921
color4=#458588
color5=#b16286
color6=#689d6a
color7=#a89984

color8=#928374
color9=#fb4934
color10=#b8bb26
color11=#fabd2f
color12=#83a598
color13=#d3869b
color14=#8ec07c
color15=#ebdbb2
```

</details>

<details>
<summary>🌸 Tokyo Night</summary>

```properties
# ═══════════════════════════════════════
# 🌸 TOKYO NIGHT
# ═══════════════════════════════════════

background=#1a1b26
foreground=#a9b1d6
cursor=#c0caf5

color0=#15161e
color1=#f7768e
color2=#9ece6a
color3=#e0af68
color4=#7aa2f7
color5=#bb9af7
color6=#7dcfff
color7=#a9b1d6

color8=#414868
color9=#f7768e
color10=#9ece6a
color11=#e0af68
color12=#7aa2f7
color13=#bb9af7
color14=#7dcfff
color15=#c0caf5
```

</details>

### 🔤 Font Configuration

#### Popular Fonts for Terminals

```bash
# Create fonts directory
mkdir -p ~/.termux/fonts
```

Download your preferred font:

| Font | Style | Download |
|------|-------|----------|
| 💎 **JetBrains Mono** | Modern, clear | [Link](https://github.com/JetBrains/JetBrainsMono) |
| ⚡ **Fira Code** | Ligatures | [Link](https://github.com/tonsky/FiraCode) |
| 🎯 **Hack** | Clean, readable | [Link](https://github.com/source-foundry/Hack) |
| 🚀 **Cascadia Code** | Microsoft's font | [Link](https://github.com/microsoft/cascadia-code) |

Or use termux-styling:

```bash
termux-style
# Navigate to fonts section
```

### 🔄 Apply Changes

After making changes:

```bash
termux-reload-settings
```

Or restart Termux.

### 🎭 Complete Theme Package

Want everything configured? Here's a full setup:

```bash
nano ~/.termux/termux.properties
```

```properties
# ═══════════════════════════════════════
# ⚙️ TERMUX PROPERTIES
# ═══════════════════════════════════════

# Allow external apps to execute commands
allow-external-apps = true

# Bell character behavior
bell-character=vibrate

# Use black for drawer and dialogs
use-black-ui = true

# Soft keyboard behavior
soft-keyboard-custom-keys=\
    [ \
        ['ESC','/','-','HOME','UP','END','PGUP'], \
        ['TAB','CTRL','ALT','LEFT','DOWN','RIGHT','PGDN'] \
    ]
```

### 🎨 Pro Styling Tips

#### 1. Test Before Committing

```bash
# Backup current theme
cp ~/.termux/colors.properties ~/.termux/colors.properties.backup

# Test new theme
nano ~/.termux/colors.properties
termux-reload-settings

# If you don't like it, restore backup
cp ~/.termux/colors.properties.backup ~/.termux/colors.properties
termux-reload-settings
```

#### 2. Match Everything

Make sure your theme matches:
- ✅ Termux colors
- ✅ Fish shell colors (in config.fish)
- ✅ Starship prompt colors (in starship.toml)
- ✅ Fastfetch colors (in config.jsonc)

#### 3. Color Preview

Test your colors:

```bash
# Show all colors
for i in {0..255}; do printf "\x1b[38;5;${i}mColor ${i}\n"; done

# 8-color test
echo -e "\e[30m Black \e[31m Red \e[32m Green \e[33m Yellow \e[34m Blue \e[35m Magenta \e[36m Cyan \e[37m White \e[0m"
```

**📚 Resources:**
- 🎨 [Termux Styling GitHub](https://github.com/adi1090x/termux-style)
- 🌈 [Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
- 🔤 [Nerd Fonts](https://www.nerdfonts.com/)
- 🎭 [Terminal Sexy](https://terminal.sexy/) - Theme creator

---

## Chapter 6: Essential Tools & Utilities

### 🛠️ Transform Your Terminal with Modern Tools!

Replace old Unix tools with modern, faster, and prettier alternatives.

### 📦 Installation Command

Install all essentials in one go:

```bash
pkg install -y \
    exa bat ripgrep fd fzf \
    htop ncdu ranger \
    git-delta micro \
    jq tldr httpie
```

---

### 📂 File Management

#### 🎨 **Exa** - Modern `ls` Replacement

```bash
pkg install -y exa
```

**Features:**
- 🎨 Colored output
- 📁 Icons support
- 🌳 Tree view
- 📅 Git integration

**Usage:**

```fish
# Basic listing with icons
exa --icons

# Detailed list
exa -la --icons

# Tree view
exa --tree --level=2 --icons

# Add to config.fish
alias ls='exa --icons'
alias la='exa -la --icons'
alias tree='exa --tree --icons'
```

#### 🦇 **Bat** - `cat` with Wings

```bash
pkg install -y bat
```

**Features:**
- 🎨 Syntax highlighting
- 📝 Line numbers
- 🔍 Git integration
- 📄 Automatic paging

**Usage:**

```fish
# View file with syntax highlighting
bat file.py

# Show line numbers
bat -n file.js

# Show git changes
bat --diff file.sh

# Add to config.fish
alias cat='bat --style=plain'
alias catn='bat --style=numbers'
alias batdiff='bat --diff'
```

#### 🔍 **Ripgrep** - Super Fast Search

```bash
pkg install -y ripgrep
```

**Usage:**

```fish
# Search in current directory
rg "search term"

# Case insensitive
rg -i "search term"

# Search specific file types
rg -t py "import"

# Show file names only
rg -l "TODO"

# Add to config.fish
alias grep='rg'
```

#### 📁 **Fd** - Better `find`

```bash
pkg install -y fd
```

**Usage:**

```fish
#