# Waybar Configuration

Custom waybar configuration for Sway with media player integration, system monitoring, and power management.

## Dependencies

### Required

```bash
# Fedora
sudo dnf install waybar sway pulseaudio pavucontrol wlogout power-profiles-daemon

# Arch
sudo pacman -S waybar sway pulseaudio pavucontrol wlogout power-profiles-daemon
```

### Fonts

```bash
# Fedora
sudo dnf install hack-fonts fontawesome-fonts

# Arch
sudo pacman -S ttf-hack-nerd otf-font-awesome
```

### Media Player Script

The `mediaplayer.py` script requires Python with GObject introspection and Playerctl:

```bash
# Fedora
sudo dnf install python3-gobject playerctl

# Arch
sudo pacman -S python-gobject playerctl
```

### Optional (for specific modules)

| Module | Package |
|--------|---------|
| `mpd` | `mpd`, `mpc` |
| `bluetooth` | `bluez`, `bluez-utils` |
| `network` | `networkmanager` |

```bash
# Fedora (optional)
sudo dnf install mpd mpc bluez

# Arch (optional)
sudo pacman -S mpd mpc bluez bluez-utils
```

## Installation

```bash
mkdir -p ~/.config/waybar
cp config.jsonc style.css mediaplayer.py ~/.config/waybar/
chmod +x ~/.config/waybar/mediaplayer.py
```

## Modules

- **Left**: Workspaces (persistent 1-5), Sway mode, Scratchpad, Media player
- **Center**: Clock with calendar tooltip
- **Right**: Tray, MPD, Idle inhibitor, PulseAudio, Network, Bluetooth, Power profiles, Battery, Power menu

## Customization

- Edit `config.jsonc` for module configuration
- Edit `style.css` for appearance
- Uncomment modules in the config to enable CPU, memory, temperature, or backlight monitoring
