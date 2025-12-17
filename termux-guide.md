# Comprehensive Termux Customization Guide

A complete guide to transforming your Termux environment into a powerful, beautiful, and efficient mobile terminal.

---

## Table of Contents

1. [Introduction](#chapter-1-introduction)
2. [Initial Setup & Prerequisites](#chapter-2-initial-setup--prerequisites)
3. [Fish Shell Installation & Configuration](#chapter-3-fish-shell-installation--configuration)
4. [Fastfetch Setup & Customization](#chapter-4-fastfetch-setup--customization)
5. [Terminal Styling & Themes](#chapter-5-terminal-styling--themes)
6. [Essential Tools & Utilities](#chapter-6-essential-tools--utilities)
7. [Productivity Enhancements](#chapter-7-productivity-enhancements)
8. [Advanced Customizations](#chapter-8-advanced-customizations)
9. [Backup & Restore](#chapter-9-backup--restore)
10. [Troubleshooting](#chapter-10-troubleshooting)

---

## Chapter 1: Introduction

### What is Termux?

Termux is a powerful terminal emulator and Linux environment for Android that works without requiring root access. This guide will help you transform it into a feature-rich development environment.

### What You'll Learn

- Setting up Fish shell for enhanced command-line experience
- Configuring Fastfetch for beautiful system information display
- Installing essential development tools
- Customizing your terminal appearance
- Boosting productivity with modern CLI tools

### Prerequisites

- Android device (5.0 or higher)
- Termux app (download from F-Droid, not Play Store)
- Stable internet connection
- Basic understanding of terminal commands

---

## Chapter 2: Initial Setup & Prerequisites

### Step 1: Install Termux

Download Termux from F-Droid (recommended):
```
https://f-droid.org/en/packages/com.termux/
```

**Important:** Avoid the Play Store version as it's outdated and no longer maintained.

### Step 2: Grant Storage Permission

Allow Termux to access your device storage:

```bash
termux-setup-storage
```

Tap "Allow" when prompted. This creates a `~/storage` directory with access to your device's files.

### Step 3: Update Packages

Update the package repository and upgrade existing packages:

```bash
pkg update && pkg upgrade -y
```

This may take a few minutes on first run.

### Step 4: Install Essential Packages

```bash
pkg install -y git curl wget nano vim
```

### Step 5: Change Repository (Optional but Recommended)

For faster downloads, change to a mirror:

```bash
termux-change-repo
```

Select a mirror close to your location.

**Resources:**
- [Termux Wiki](https://wiki.termux.com/)
- [Termux Documentation](https://termux.dev/)

---

## Chapter 3: Fish Shell Installation & Configuration

### What is Fish Shell?

Fish (Friendly Interactive Shell) offers autosuggestions, syntax highlighting, and a modern scripting syntax out of the box.

### Step 1: Install Fish

```bash
pkg install -y fish
```

### Step 2: Set Fish as Default Shell

```bash
chsh -s fish
```

Restart Termux for changes to take effect.

### Step 3: Configure Fish

Create Fish config directory:

```bash
mkdir -p ~/.config/fish
```

Create configuration file:

```bash
nano ~/.config/fish/config.fish
```

Add basic configuration:

```fish
# Disable greeting
set fish_greeting

# Set color scheme
set -g fish_color_command green
set -g fish_color_param cyan
set -g fish_color_error red
set -g fish_color_quote yellow

# Aliases
alias ll='ls -alh'
alias ..='cd ..'
alias ...='cd ../..'
alias cls='clear'
alias update='pkg update && pkg upgrade'
```

Save with `Ctrl+X`, then `Y`, then `Enter`.

### Step 4: Install Fisher (Plugin Manager)

```bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
```

### Step 5: Install Popular Fish Plugins

```bash
# Syntax highlighting
fisher install jorgebucaran/autopair.fish

# Better directory navigation
fisher install jethrokuan/z

# Colored man pages
fisher install decors/fish-colored-man
```

### Step 6: Install Starship Prompt (Optional)

Starship provides a beautiful, fast, and customizable prompt:

```bash
pkg install -y starship
```

Add to `~/.config/fish/config.fish`:

```fish
starship init fish | source
```

**Resources:**
- [Fish Shell Documentation](https://fishshell.com/docs/current/)
- [Fisher Plugin Manager](https://github.com/jorgebucaran/fisher)
- [Starship Prompt](https://starship.rs/)

---

## Chapter 4: Fastfetch Setup & Customization

### What is Fastfetch?

Fastfetch is a fast system information tool written in C, perfect for displaying system specs when you open a terminal.

### Step 1: Install Fastfetch

```bash
pkg install -y fastfetch
```

### Step 2: Test Default Configuration

```bash
fastfetch
```

You should see your system information displayed with ASCII art.

### Step 3: Create Custom Configuration

Create config directory:

```bash
mkdir -p ~/.config/fastfetch
```

Create configuration file:

```bash
nano ~/.config/fastfetch/config.jsonc
```

Add custom configuration:

```jsonc
{
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "logo": {
        "source": "android",
        "padding": {
            "top": 1,
            "left": 2
        }
    },
    "display": {
        "separator": " → ",
        "color": "green"
    },
    "modules": [
        "title",
        "separator",
        "os",
        "host",
        "kernel",
        "uptime",
        "packages",
        "shell",
        "terminal",
        "cpu",
        "memory",
        "disk",
        "battery",
        "locale",
        "break",
        "colors"
    ]
}
```

### Step 4: Auto-run Fastfetch on Startup

Add to `~/.config/fish/config.fish`:

```fish
# Display system info on startup
if status is-interactive
    fastfetch
end
```

### Step 5: Create Custom ASCII Art (Optional)

Create your own ASCII art file:

```bash
nano ~/.config/fastfetch/logo.txt
```

Add your custom ASCII art, then modify config:

```jsonc
"logo": {
    "source": "~/.config/fastfetch/logo.txt",
    "type": "file"
}
```

**Resources:**
- [Fastfetch GitHub](https://github.com/fastfetch-cli/fastfetch)
- [Fastfetch Wiki](https://github.com/fastfetch-cli/fastfetch/wiki)
- [ASCII Art Generator](https://www.asciiart.eu/)

---

## Chapter 5: Terminal Styling & Themes

### Step 1: Install Color Schemes

Termux supports color customization through `.termux` directory:

```bash
mkdir -p ~/.termux
```

### Step 2: Browse Available Themes

Install Termux styling package:

```bash
pkg install -y termux-styling
```

Run the styling tool:

```bash
termux-style
```

Use volume keys to navigate and select a color scheme.

### Step 3: Manual Color Configuration

Create custom color scheme:

```bash
nano ~/.termux/colors.properties
```

Example (Dracula theme):

```properties
# Dracula Theme
background=#282a36
foreground=#f8f8f2
cursor=#f8f8f2

color0=#000000
color1=#ff5555
color2=#50fa7b
color3=#f1fa8c
color4=#bd93f9
color5=#ff79c6
color6=#8be9fd
color7=#bfbfbf

color8=#4d4d4d
color9=#ff6e67
color10=#5af78e
color11=#f4f99d
color12=#caa9fa
color13=#ff92d0
color14=#9aedfe
color15=#e6e6e6
```

### Step 4: Font Customization

Create font configuration:

```bash
nano ~/.termux/font.ttf
```

Download and place your favorite monospace font (JetBrains Mono, Fira Code, etc.)

Or use termux-styling:

```bash
termux-style
```

Select fonts from the list.

### Step 5: Reload Settings

```bash
termux-reload-settings
```

**Resources:**
- [Termux Styling](https://github.com/adi1090x/termux-style)
- [Color Schemes Collection](https://github.com/mbadolato/iTerm2-Color-Schemes)
- [Nerd Fonts](https://www.nerdfonts.com/)

---

## Chapter 6: Essential Tools & Utilities

### File Management

```bash
# Advanced file manager
pkg install -y ranger

# Modern ls replacement
pkg install -y exa

# Disk usage analyzer
pkg install -y ncdu

# File search tool
pkg install -y fd
```

### Text Editors

```bash
# Vim with modern features
pkg install -y neovim

# Nano (already installed)
# Emacs
pkg install -y emacs
```

### System Monitoring

```bash
# System monitor
pkg install -y htop

# Network monitoring
pkg install -y iftop

# Process viewer
pkg install -y glances
```

### Development Tools

```bash
# Python
pkg install -y python

# Node.js
pkg install -y nodejs

# Go
pkg install -y golang

# Rust
pkg install -y rust

# Build essentials
pkg install -y clang make cmake
```

### Network Tools

```bash
# Download manager
pkg install -y aria2

# HTTP client
pkg install -y httpie

# Network scanner
pkg install -y nmap

# SSH client (already included)
```

### Media Tools

```bash
# Image viewer
pkg install -y termimage

# Music player
pkg install -y mpv

# Video player
pkg install -y ffmpeg

# Image manipulation
pkg install -y imagemagick
```

**Resources:**
- [Termux Packages](https://github.com/termux/termux-packages)
- [Awesome Termux](https://github.com/TermuxArch/awesome-termux)

---

## Chapter 7: Productivity Enhancements

### Better Command-Line Tools

Install modern replacements for classic Unix tools:

```bash
# bat: cat with syntax highlighting
pkg install -y bat

# ripgrep: faster grep
pkg install -y ripgrep

# fzf: fuzzy finder
pkg install -y fzf

# tldr: simplified man pages
pkg install -y tealdeer
```

### Configure Aliases in Fish

Add to `~/.config/fish/config.fish`:

```fish
# Modern tool aliases
alias cat='bat'
alias grep='rg'
alias find='fd'
alias ls='exa --icons'
alias la='exa -la --icons'
alias tree='exa --tree --icons'

# Quick navigation
alias h='cd ~'
alias d='cd ~/storage/downloads'
alias dc='cd ~/storage/dcim'

# Quick edit
alias fishconfig='nano ~/.config/fish/config.fish'
alias ffconfig='nano ~/.config/fastfetch/config.jsonc'

# Git shortcuts
alias gs='git status'
alias ga='git add'
alias gc='git commit'
alias gp='git push'
alias gl='git log --oneline --graph'
```

### FZF Integration with Fish

Add FZF key bindings:

```bash
fzf_key_bindings
```

Add to config:

```fish
# FZF configuration
set -gx FZF_DEFAULT_OPTS '--height 40% --layout=reverse --border'
set -gx FZF_DEFAULT_COMMAND 'fd --type f'
```

### Setup Z for Directory Jumping

Already installed via Fisher. Usage:

```bash
# Visit directories
cd ~/storage/downloads
cd ~/documents
cd ~/.config

# Jump using z
z down      # Goes to downloads
z doc       # Goes to documents
z conf      # Goes to .config
```

### Clipboard Integration

```bash
# Install termux-api
pkg install -y termux-api

# Install the Termux:API app from F-Droid
```

Add functions to `config.fish`:

```fish
# Copy to clipboard
function clip
    termux-clipboard-set
end

# Paste from clipboard
function paste
    termux-clipboard-get
end
```

**Resources:**
- [Modern Unix Tools](https://github.com/ibraheemdev/modern-unix)
- [FZF Examples](https://github.com/junegunn/fzf/wiki/examples)
- [Termux:API](https://wiki.termux.com/wiki/Termux:API)

---

## Chapter 8: Advanced Customizations

### Custom Fish Functions

Create custom functions directory:

```bash
mkdir -p ~/.config/fish/functions
```

Example: Create a backup function:

```bash
nano ~/.config/fish/functions/backup.fish
```

```fish
function backup --description 'Backup important files'
    set backup_dir ~/backups/(date +%Y-%m-%d)
    mkdir -p $backup_dir
    
    cp -r ~/.config $backup_dir/
    cp ~/.termux/colors.properties $backup_dir/
    
    echo "Backup created at $backup_dir"
end
```

### Auto-suggestions Configuration

Configure Fish auto-suggestions:

```fish
# Add to config.fish
set -g fish_autosuggestion_enabled 1
set -g fish_color_autosuggestion 555
```

### Custom Prompt with Starship

Create Starship config:

```bash
mkdir -p ~/.config
nano ~/.config/starship.toml
```

```toml
# Minimal prompt
format = """
[┌─](bold green)$directory$git_branch$git_status
[└─](bold green)$character"""

[character]
success_symbol = "[➜](bold green)"
error_symbol = "[✗](bold red)"

[directory]
truncation_length = 3
truncate_to_repo = true
style = "bold cyan"

[git_branch]
symbol = " "
style = "bold purple"

[git_status]
style = "bold yellow"
```

### Script Automation

Create a scripts directory:

```bash
mkdir -p ~/scripts
```

Example: System update script:

```bash
nano ~/scripts/update-system.sh
```

```bash
#!/data/data/com.termux/files/usr/bin/bash

echo "Updating packages..."
pkg update && pkg upgrade -y

echo "Updating Fisher plugins..."
fisher update

echo "System updated successfully!"
```

Make executable:

```bash
chmod +x ~/scripts/update-system.sh
```

Add alias:

```fish
alias sysupdate='~/scripts/update-system.sh'
```

### Neovim Configuration (Optional)

Basic Neovim setup:

```bash
mkdir -p ~/.config/nvim
nano ~/.config/nvim/init.vim
```

```vim
" Basic settings
set number
set relativenumber
set autoindent
set tabstop=4
set shiftwidth=4
set smarttab
set softtabstop=4
set mouse=a
syntax on
```

**Resources:**
- [Fish Functions](https://fishshell.com/docs/current/cmds/function.html)
- [Starship Configuration](https://starship.rs/config/)
- [Neovim Documentation](https://neovim.io/doc/)

---

## Chapter 9: Backup & Restore

### Manual Backup

Create backup script:

```bash
nano ~/scripts/backup-termux.sh
```

```bash
#!/data/data/com.termux/files/usr/bin/bash

BACKUP_DIR=~/storage/downloads/termux-backup-$(date +%Y%m%d)
mkdir -p $BACKUP_DIR

# Backup configurations
cp -r ~/.config $BACKUP_DIR/
cp -r ~/.termux $BACKUP_DIR/
cp ~/.bashrc $BACKUP_DIR/ 2>/dev/null
cp ~/scripts $BACKUP_DIR/ -r 2>/dev/null

# Create package list
pkg list-installed > $BACKUP_DIR/packages.txt

echo "Backup completed: $BACKUP_DIR"
```

Make executable:

```bash
chmod +x ~/scripts/backup-termux.sh
```

### Restore from Backup

Create restore script:

```bash
nano ~/scripts/restore-termux.sh
```

```bash
#!/data/data/com.termux/files/usr/bin/bash

if [ -z "$1" ]; then
    echo "Usage: restore-termux.sh <backup-directory>"
    exit 1
fi

BACKUP_DIR=$1

# Restore configurations
cp -r $BACKUP_DIR/.config ~/
cp -r $BACKUP_DIR/.termux ~/
cp $BACKUP_DIR/.bashrc ~/ 2>/dev/null
cp -r $BACKUP_DIR/scripts ~/ 2>/dev/null

# Install packages
if [ -f "$BACKUP_DIR/packages.txt" ]; then
    echo "Reinstalling packages..."
    cat $BACKUP_DIR/packages.txt | xargs pkg install -y
fi

echo "Restore completed!"
termux-reload-settings
```

### Git-based Backup

Initialize git repository for configs:

```bash
cd ~
mkdir termux-config
cd termux-config

# Copy configurations
cp -r ~/.config .
cp -r ~/.termux .
cp ~/scripts . -r

# Initialize git
git init
git add .
git commit -m "Initial commit"

# Push to GitHub
git remote add origin https://github.com/itachi-re/termux-customization.git
git branch -M main
git push -u origin main
```

**Resources:**
- [Termux Backup Guide](https://wiki.termux.com/wiki/Backing_up_Termux)
- [Git Documentation](https://git-scm.com/doc)

---

## Chapter 10: Troubleshooting

### Common Issues

**Issue 1: Fish shell not starting**

Solution:
```bash
# Reset to bash
chsh -s bash
# Restart Termux and reinstall Fish
pkg reinstall fish
chsh -s fish
```

**Issue 2: Fastfetch not displaying**

Solution:
```bash
# Check installation
which fastfetch

# Reinstall
pkg reinstall fastfetch

# Test with verbose mode
fastfetch --version
```

**Issue 3: Permission denied errors**

Solution:
```bash
# Run storage setup again
termux-setup-storage

# Check file permissions
ls -la filename

# Fix permissions
chmod +x filename
```

**Issue 4: Package installation fails**

Solution:
```bash
# Clear package cache
pkg clean

# Update repositories
pkg update

# Try again
pkg upgrade
```

**Issue 5: Colors not working**

Solution:
```bash
# Check termux colors file
cat ~/.termux/colors.properties

# Reload settings
termux-reload-settings

# Reinstall termux-styling
pkg reinstall termux-styling
```

### Performance Tips

1. **Reduce startup time:**
   - Remove unnecessary plugins
   - Lazy-load heavy tools
   - Optimize Fish config

2. **Save battery:**
   - Close unused sessions
   - Disable background services
   - Use lightweight tools

3. **Free up space:**
```bash
# Clean package cache
pkg clean

# Remove orphaned packages
pkg autoclean

# Check disk usage
ncdu ~
```

### Useful Commands

```bash
# Check Fish config for errors
fish --debug

# List all aliases
alias

# Check environment variables
env

# Reload Fish config
source ~/.config/fish/config.fish

# Reset terminal
reset
```

### Getting Help

```bash
# Man pages
man command-name

# TLDR pages (simplified)
tldr command-name

# Package info
pkg show package-name

# Fish help
help command-name
```

**Resources:**
- [Termux Community](https://www.reddit.com/r/termux/)
- [Fish Shell Gitter](https://gitter.im/fish-shell/fish-shell)
- [Termux GitHub Issues](https://github.com/termux/termux-app/issues)

---

## Bonus: Quick Setup Script

Save this as `setup.sh` in your repository:

```bash
#!/data/data/com.termux/files/usr/bin/bash

echo "Starting Termux customization setup..."

# Update system
pkg update && pkg upgrade -y

# Install essential packages
pkg install -y fish git curl wget nano vim fastfetch exa bat ripgrep fd fzf

# Setup Fish
chsh -s fish
mkdir -p ~/.config/fish

# Install Fisher
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher

# Install Fish plugins
fish -c "fisher install jorgebucaran/autopair.fish"
fish -c "fisher install jethrokuan/z"

# Setup Fastfetch config
mkdir -p ~/.config/fastfetch

# Setup termux styling
pkg install -y termux-styling

echo "Setup complete! Restart Termux to apply changes."
```

Run with:
```bash
bash setup.sh
```

---

## Contributing

Feel free to contribute to this guide by:
- Opening issues for corrections
- Submitting pull requests with improvements
- Sharing your custom configurations

## License

MIT License - Feel free to use and modify

---

## Additional Resources

### Official Documentation
- [Termux Wiki](https://wiki.termux.com/)
- [Fish Shell Documentation](https://fishshell.com/docs/current/)
- [Fastfetch GitHub](https://github.com/fastfetch-cli/fastfetch)

### Community Resources
- [r/termux](https://www.reddit.com/r/termux/)
- [Termux Discord](https://discord.gg/termux)
- [Fish Shell Gitter](https://gitter.im/fish-shell/fish-shell)

### Useful GitHub Repositories
- [Awesome Termux](https://github.com/TermuxArch/awesome-termux)
- [Termux Packages](https://github.com/termux/termux-packages)
- [Modern Unix](https://github.com/ibraheemdev/modern-unix)

### Video Tutorials
- Search YouTube for "Termux customization"
- Search YouTube for "Fish shell tutorial"

---

**Last Updated:** December 2025  
**Repository:** https://github.com/itachi-re/termux-customization.git