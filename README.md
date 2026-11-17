# boring-wm

My Hyprland config, and an AeroSpace config for the MacBook so my hands do
the same thing on both. Black, no wallpaper, no gaps, borders, blur, shadows
or rounding. One mint accent (`#94e2d5`), a flat 24px waybar, and a hyprlock
that looks like a getty prompt.

## Hyprland

Needs Hyprland 0.54+, waybar, ghostty, rofi, mako, swayosd, cliphist and
hyprlock. The hyprview plugin is optional and only used for F4.

```bash
git clone https://github.com/teddytennant/boring-wm.git && cd boring-wm
mv ~/.config/hypr ~/.config/hypr.bak; mv ~/.config/waybar ~/.config/waybar.bak
ln -s "$(pwd)/hyprland" ~/.config/hypr
ln -s "$(pwd)/hyprland/waybar" ~/.config/waybar
hyprctl reload
```

| key | |
|---|---|
| `Super+Return` | ghostty |
| `Super+Space` | rofi |
| `Super+Q` | close |
| `Super+F` | fullscreen |
| `Super+H/J/K/L` | focus |
| `Super+Shift+H/J/K/L` | swap |
| `Super+Alt+H/J/K/L` | resize |
| `Super+1-9,0` | workspace 1-10 |
| `Super+Shift+1-9,0` | move to workspace |
| `Super+B/Z/O` | Brave, Zed, Obsidian |
| `Super+[` | float |
| `Super+X` | toggle split |
| `F4` | overview |
| `Ctrl+Alt+Q` | lock |

## AeroSpace

```bash
mv ~/.aerospace.toml ~/.aerospace.toml.bak
ln -s "$(pwd)/macos/aerospace.toml" ~/.aerospace.toml
aerospace reload-config
```

Same letters with `cmd` in place of `Super`, except close is `cmd-shift-q`.
`cmd-space` opens Raycast, so turn off the Spotlight shortcut in System
Settings or change it in `aerospace.toml`.
