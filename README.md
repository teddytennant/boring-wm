# boring-wm

Brutalist window management: pure black, zero chrome, vim-style navigation. Hyprland config for Linux, AeroSpace adaptation for macOS.

## Philosophy

- **Boring theme**: black & white palette, mint accent (`#94e2d5`), no wallpaper, no blur, no shadows, no gaps, no borders
- **Flat waybar**: 24px strip, workspace numbers, no rounded corners
- **TTY lock screen**: getty-style hyprlock on Linux
- **Same muscle memory** across Hyprland (NixOS) and AeroSpace (MacBook Air)

## Hyprland (Linux)

### Requirements

- Hyprland 0.54+
- waybar, ghostty, rofi, mako, swayosd, cliphist, hyprlock
- Optional: hyprview plugin (F4 overview)

### Install

```bash
git clone git@github.com:teddytennant/boring-wm.git
cd boring-wm

# Back up existing config
mv ~/.config/hypr ~/.config/hypr.bak 2>/dev/null || true
mv ~/.config/waybar ~/.config/waybar.bak 2>/dev/null || true

# Symlink boring config
mkdir -p ~/.config
ln -s "$(pwd)/hyprland" ~/.config/hypr
ln -s "$(pwd)/hyprland/waybar" ~/.config/waybar

# Start waybar with boring config
pkill waybar 2>/dev/null || true
waybar -c ~/.config/waybar/config -s ~/.config/waybar/style.css &
```

Point your Hyprland install at `~/.config/hypr/hyprland.conf` (default). Reload with `hyprctl reload`.

### Keybinds

| Binding | Action |
|---------|--------|
| `Super+Return` | Terminal (ghostty) |
| `Super+Space` | App launcher (rofi) |
| `Super+Q` | Close window |
| `Super+F` | Fullscreen |
| `Super+H/J/K/L` | Focus left/down/up/right |
| `Super+Shift+H/J/K/L` | Swap window |
| `Super+Alt+H/J/K/L` | Resize window |
| `Super+1–9,0` | Workspace 1–10 |
| `Super+Shift+1–9,0` | Move window to workspace |
| `Super+B/Z/O` | Brave / Zed / Obsidian |
| `Super+[` | Toggle floating |
| `Super+X` | Toggle split |
| `F4` | Window overview (hyprview) |
| `Ctrl+Alt+Q` | Lock screen |

## AeroSpace (macOS)

### Requirements

- [AeroSpace](https://github.com/nikitabobko/AeroSpace) installed via Homebrew
- Ghostty, Brave, Obsidian (or edit app names in config)

### Install

```bash
git clone git@github.com:teddytennant/boring-wm.git
cd boring-wm

# Back up existing config
mv ~/.aerospace.toml ~/.aerospace.toml.bak 2>/dev/null || true

ln -s "$(pwd)/macos/aerospace.toml" ~/.aerospace.toml
aerospace reload-config
```

**Note:** `cmd-space` is bound to the app launcher. Disable the Spotlight shortcut in System Settings → Keyboard → Keyboard Shortcuts → Spotlight, or change the binding in `aerospace.toml`.

### Keybind mapping

Hyprland `Super` → AeroSpace `cmd`. Same letter bindings as the Linux config above.

| Hyprland | AeroSpace | Action |
|----------|-----------|--------|
| `Super+Return` | `cmd-enter` | Terminal |
| `Super+Space` | `cmd-space` | Launcher |
| `Super+Q` | `cmd-shift-q` | Close window |
| `Super+H/J/K/L` | `cmd-h/j/k/l` | Focus |
| `Super+Shift+H/J/K/L` | `cmd-shift-h/j/k/l` | Move window |
| `Super+Alt+H/J/K/L` | `cmd-alt-h/j/k/l` | Resize |
| `Super+1–9` | `cmd-1–9` | Workspace |
| `Super+0` | `cmd-0` | Workspace 10 |
| `Super+B/Z/O` | `cmd-b/z/o` | Apps |

## License

Private config — all yours.