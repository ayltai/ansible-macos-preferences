# macOS customization role for Ansible

[![GitHub workflow status](https://img.shields.io/github/workflow/status/ayltai/ansible-macos-preferences/CI?style=flat)](https://github.com/ayltai/ansible-macos-preferences/actions)
[![Ansible quality score](https://img.shields.io/badge/quality-5-success)](https://galaxy.ansible.com/ayltai/macos_preferences)
[![Ansible role](https://img.shields.io/badge/role-ayltai.macos_preferences-blue)](https://galaxy.ansible.com/ayltai/macos_preferences)
![Maintenance](https://img.shields.io/maintenance/yes/2022?style=flat)
[![Release](https://img.shields.io/github/release/ayltai/ansible-macos-preferences.svg?style=flat)](https://github.com/ayltai/ansible-macos-preferences/releases)
[![License](https://img.shields.io/github/license/ayltai/ansible-macos-preferences.svg?style=flat)](https://github.com/ayltai/ansible-macos-preferences/blob/master/LICENSE)

Applies macOS customizations.

[![Buy me a coffee](https://img.shields.io/static/v1?label=Buy%20me%20a&message=coffee&color=important&style=flat&logo=buy-me-a-coffee&logoColor=white)](https://buymeacoff.ee/ayltai)

## Quick start

Make sure you have [Homebrew](https://brew.sh) installed on macOS.

### Installation
```sh
ansible-galaxy install ayltai.macos_preferences
```

### Usage
```yaml
---
- hosts: all
  roles:
    - ayltai.macos_preferences
  vars:
    macos_default_shell: bash
```

## Variables
| Name | Type | Default | Description |
|------|------|---------|-------------|
| `macos_pause` | `integer` | 10 | Controls how long to wait before an information message is dismissed automatically. |
| `macos_launchpad_grid_columns` | `integer` | 4 | Changes [Launchpad](https://support.apple.com/HT202635) layout to this many columns. |
| `macos_launchpad_grid_rows` | `integer` | 3 | Changes [Launchpad](https://support.apple.com/HT202635) layout to this many rows. |
| `macos_disable_disk_image_verification` | `boolean` | Yes | Disables disk image verification. |
| `macos_disable_gate_keeper` | `boolean` | Yes | Disables [Gatekeeper](https://support.apple.com/HT202491)
| `macos_disable_game_center` | `boolean` | Yes | Disables [Game Center](https://developer.apple.com/game-center). Requires [SIP](https://support.apple.com/HT204899) to be disabled. |
| `macos_disable_smart_quotes` | `boolean` | Yes | Disables smart quotes feature. |
| `macos_disable_smart_dashes` | `boolean` | Yes | Disables smart dashes feature. |
| `macos_disable_sms` | `boolean` | Yes | Disables Sudden Motion Sensor. |
| `macos_disable_hibernation` | `boolean` | Yes | Disables hibernation. Requires [SIP](https://support.apple.com/HT204899) to be disabled. |
| `macos_disable_photos_auto_open` | `boolean` | Yes | Disables [Photos](https://www.apple.com/macos/photos) from opening automatically. |
| `macos_ask_password_immediately` | `boolean` | Yes | Prompts for password immediately after screen is off or screensaver starts. |
| `macos_enable_subpixel_font_rendering` | `boolean` | Yes | Enables sub-pixel rendering on external monitors. |
| `macos_default_screenshot_format` | `string` | `png` | Sets the default image format for screenshots. Supports `jpg`, `tiff`, `gif`, `pdf` and `png`. |
| `macos_default_screenshot_location` | `path` | `{{ macos_default_finder_location }}` | Sets the default location to save screenshots. |
| `macos_default_finder_location` | `path` | `~/Downloads` | Sets the default location for new [Finder](https://support.apple.com/HT201732) windows. |
| `macos_show_finder_file_extension` | `boolean` | Yes | Shows file extensions in [Finder](https://support.apple.com/HT201732). |
| `macos_show_finder_status_bar` | `boolean` | Yes | Shows the status bar in [Finder](https://support.apple.com/HT201732). |
| `macos_show_finder_quit` | `boolean` | Yes | Shows "Quit" menu item for [Finder](https://support.apple.com/HT201732). |
| `macos_finder_sort_folder` | `boolean` | Yes | Shows folders on top when sorted by filename in [Finder](https://support.apple.com/HT201732). |
| `macos_disable_file_extension_warning` | `boolean` | Yes | Disable the warning about file extension changes in [Finder](https://support.apple.com/HT201732). |
| `macos_default_finder_view_style` | `string` | `Nlsv` | Sets the default view style in [Finder](https://support.apple.com/HT201732). Supports `Flwv` (cover flow view), `Nlsv` (list view), `clmv` (column view) and `icnv` (icon view). |
| `macos_spring_loading_enabled` | `boolean` | Yes | Enables spring loading in [Finder](https://support.apple.com/HT201732). |
| `macos_spring_loading_delay` | `integer` | 1 | Sets the spring loading delay in [Finder](https://support.apple.com/HT201732). |
| `macos_disable_ds_store` | `boolean` | Yes | Disables the creation of `.DS_Store` files on network drives. |
| `macos_disable_empty_trash_warning` | `boolean` | Yes | Disables the warning about emptying Trash. |
| `macos_dock_position` | `string` | `right` | Sets the [Dock](https://support.apple.com/guide/macbook-air/apd4b7fb731f/mac) position. Supports `left`, `right` and `bottom`. |
| `macos_dock_tile_size` | `integer` | 32 | Sets the [Dock](https://support.apple.com/guide/macbook-air/apd4b7fb731f/mac) size in pixels. |
| `macos_dock_lock_size` | `boolean` | Yes | Disable manual resizing of the [Dock](https://support.apple.com/guide/macbook-air/apd4b7fb731f/mac). |
| `macos_dock_spring_loading` | `boolean` |  Yes | Enables spring loading in the [Dock](https://support.apple.com/guide/macbook-air/apd4b7fb731f/mac). |
| `macos_dock_hide_recent_apps` | `boolean` | Yes | Disables showing recent applications in the [Dock](https://support.apple.com/guide/macbook-air/apd4b7fb731f/mac). |
| `macos_terminal_encoding_utf8` | `boolean` | Yes | Sets the default character encoding to UTF-8 in [Terminal](https://support.apple.com/guide/terminal/welcome/mac). |
| `macos_default_terminal_theme` | `string` | `Pro` | Sets the default [Terminal](https://support.apple.com/guide/terminal/welcome/mac) theme. |
| `macos_disable_chrome_swipe_navigation` | `boolean` | Yes | Disable swipe navigation in [Google Chrome](https://www.google.com/intl/en_us/chrome). |
| `macos_disable_itunes_media_keys` | `boolean` | Yes | Disables [iTunes](https://www.apple.com/itunes) Media Keys. Requires [SIP](https://support.apple.com/HT204899) to be disabled. |
| `macos_default_dark_mode` | `boolean` | Yes | Turns on [Dark Mode](https://support.apple.com/HT208976) by default. |
| `macos_accent_color` | `integer` | -1 | Sets the accent color. Supports `nil` (blue), -1 (graphite), 0 (red), 1 (orange), 2 (yellow), 3 (green), 4 (blue), 5 (purple) and 6 (pink). |
| `macos_highlight_color` | `string` | `0.847059 0.847059 0.862745` | Sets the highlight color. Supports RGB values ranging from 0 to 1 in format `R G B`. |
| `macos_disable_shake_mouse` | `boolean` | Yes | Disables shaking mouse pointer to locate feature. |
| `macos_display_sleep` | `integer` | 10 | Sets the idle time before the display goes off. Sets it to 0 to disable the display from going off. |
| `macos_computer_sleep` | `integer` | 0 | Sets the idle time before the computer goes to sleep. Sets it to 0 to disable the computer from sleeping. |
| `macos_disable_sleep` | `boolean` | Yes | Disables the computer from sleeping. This will in turn set `macos_computer_sleep` to 0. |
| `macos_quit_always_saves_windows` | `boolean` | Yes | Saves windows when macOS restarts or shuts down. |
| `macos_faster_time_machine_backup` | `boolean` | Yes | Enables faster [Time Machine](https://support.apple.com/HT201250) backup by disabling CPU throttling. |
| `macos_disable_memory_compression` | `boolean` | Yes | Disable memory compression. Requires [SIP](https://support.apple.com/HT204899) to be disabled. |
| `macos_disable_crash_report` | `boolean` | Yes | Disables crash reports. Requires [SIP](https://support.apple.com/HT204899) to be disabled. |
| `macos_update_frequency` | `integer` | 1 | Sets the update frequency of macOS in number of days. |
| `macos_default_shell` | `string` | `bash` | Sets the default shell. Supports `bash`, `fish`, `ksh`, `tcsh`, and `zsh`. |

## License
[MIT](https://github.com/ayltai/ansible-macos-preferences/blob/master/LICENSE)

## References
* [Ansible](https://www.ansible.com)
* [Ansible Galaxy](https://galaxy.ansible.com)
