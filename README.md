# MSR SoftEther Panel
[راهنمای فارسی](README.fa.md)

Web-based management and quota control panel for SoftEther VPN.

## Features

- Web-based MSR management panel
- SoftEther user management
- Add users from the Web Panel
- Add users from the Admin Telegram Bot
- Per-user traffic quota management
- Service expiration date management
- Add service days
- Increase user quota
- User enable/disable management
- User deletion
- Password management
- User reset without affecting historical usage
- Per-user simultaneous connection limit
- User Telegram Bot
- Telegram account linking and removal
- Traffic usage tracking
- Quota state management
- Web dashboard with CPU, RAM, disk and live network statistics
- Panel user authentication
- CSRF protection for sensitive web actions
- MSR Panel API
- Unix socket based API service
- Systemd-based background services and timers
- Configurable HTTPS panel port during installation
- Safe upgrade handling for existing configuration and service state
- Apache configuration management

## Requirements

- Ubuntu/Debian Linux
- Apache2
- PHP
- Python 3
- SoftEther VPN Server
- SoftEther VPN Command Line Utility
- systemd

## Installation

### Direct Installation

wget https://github.com/lakymood/MSR-panel/releases/download/v1.2.0/msr-softether-panel_1.2.0.deb
sudo apt install -y ./msr-softether-panel_1.2.0.deb

### Local Installation

sudo apt install -y ./msr-softether-panel_1.2.0.deb

## Web Panel Port

Default HTTPS panel port:

1033

The port can be changed during installation.

## Telegram Services

On a fresh installation:

- The Admin Telegram Bot service starts automatically only when an admin bot token is configured.
- The User Telegram Bot service starts automatically only when a user bot token is configured.
- The notification checker timer starts automatically when a user bot token is configured.

During an upgrade, the existing Telegram service state is preserved.

## Verify Installation

dpkg -s msr-softether-panel

Check services:

systemctl status msrpanel.socket
systemctl status softether-quota.timer
systemctl status softether-telegram-bot.service
systemctl status softether-user-telegram-bot.service
systemctl status softether-notification-checker.timer

Check API socket:

ls -l /run/msrpanel/api.sock

## Upgrade

sudo apt install -y ./msr-softether-panel_1.2.0.deb

Existing configuration, quota database, state data and Telegram credentials are preserved during upgrades.

Existing Telegram service state is not changed during an upgrade.

## Remove

sudo apt remove msr-softether-panel

Managed services are disabled and the Apache site is removed. Existing configuration and user data are intentionally preserved.

## SHA256

61cdc7529f59594df8a420b76d51d978b13b1eb1d4f93715ff062375bb471d3e

Verify:

sha256sum msr-softether-panel_1.2.0.deb

## Package Information

| Item | Value |
|---|---|
| Package | msr-softether-panel |
| Version | 1.2.0 |
| Architecture | all |
| Default HTTPS Port | 1033 |
| Package Type | Debian .deb |

## Security Notes

- Do not publish Telegram bot tokens.
- Do not publish production configuration files.
- Do not publish SoftEther user passwords.
- Do not publish production database files.
- Use HTTPS when exposing the management panel over an untrusted network.

## Release

Current release: v1.2.0

The Debian package is available from the GitHub Releases section.
