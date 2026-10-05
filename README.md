# MSR SoftEther Panel
[راهنمای فارسی](README.fa.md)

Web-based management and quota control panel for SoftEther VPN.

## Features

- Web-based MSR management panel
- SoftEther user management
- Per-user traffic quota management
- Service expiration date management
- Add users from the Web Panel
- Add users from the Admin Telegram Bot
- User Telegram Bot
- Traffic usage tracking
- Quota state management
- User enable/disable management
- User deletion
- Password management
- Panel user authentication
- CSRF protection for sensitive web actions
- MSR Panel API
- Systemd-based background services
- Configurable Apache panel port

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

```bash
wget https://github.com/lakymood/MSR-panel/releases/download/v1.1.1/msr-softether-panel_1.1.1.deb && sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

### Local Installation

```bash
sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

## Web Panel Port

Default port:

```text
8080
```

The port can be changed during installation.

## Verify Installation

```bash
dpkg -s msr-softether-panel
```

Check services:

```bash
systemctl status msrpanel.socket
systemctl status softether-quota.timer
systemctl status softether-telegram-bot.service
systemctl status softether-user-telegram-bot.service
```

## Upgrade

```bash
sudo apt install -y ./msr-softether-panel_1.1.1.deb
```

## SHA256

```text
8bfdb4b09ce879b3c3b0b28f95e81bb91a39885d210966d7767d3afd73bd274c
```

Verify:

```bash
sha256sum msr-softether-panel_1.1.1.deb
```

## Package Information

| Item | Value |
|---|---|
| Package | msr-softether-panel |
| Version | 1.1.1 |
| Architecture | all |
| Default Web Port | 8080 |
| Package Type | Debian .deb |

## Security Notes

- Do not publish Telegram bot tokens.
- Do not publish production configuration files.
- Do not publish SoftEther user passwords.
- Do not publish production database files.
- Use HTTPS when exposing the management panel over an untrusted network.

## Release

Current release:

v1.1.1

The Debian package is available from the GitHub Releases section.
