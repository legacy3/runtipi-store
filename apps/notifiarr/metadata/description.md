# Notifiarr

Notifiarr is a unified notification platform that connects your *arr applications (Sonarr, Radarr, Lidarr, Readarr, etc.) and media servers to various notification services. It provides real-time notifications for downloads, upgrades, health checks, and more.

## Features

- **Unified Notifications**: Single platform for all your *arr application notifications
- **Multiple Services**: Support for Discord, Telegram, Slack, Pushover, and many more
- **Real-time Updates**: Instant notifications for downloads, upgrades, and system events
- **Health Monitoring**: Track the health of your applications and services
- **Custom Triggers**: Configure custom notification triggers and conditions
- **Rich Content**: Send detailed information including artwork, progress, and metadata
- **Web Interface**: Easy-to-use web dashboard for configuration and monitoring

## Supported Applications

- **Sonarr**: TV show management and notifications
- **Radarr**: Movie management and notifications  
- **Lidarr**: Music management and notifications
- **Readarr**: Book/audiobook management and notifications
- **Prowlarr**: Indexer management notifications
- **Bazarr**: Subtitle management notifications
- **Overseerr/Jellyseerr**: Request management notifications
- **Tautulli**: Plex/Jellyfin monitoring notifications
- **qBittorrent/Deluge**: Torrent client notifications

## Notification Services

- Discord (with rich embeds and bot integration)
- Telegram (with inline keyboards)
- Slack (with threaded messages)
- Pushover (with priority levels)
- Email (SMTP support)
- Webhooks (custom integrations)
- And many more...

## Getting Started

1. Install Notifiarr through Runtipi
2. Access the web interface at the configured port (5454)
3. Configure your notification services in the settings
4. Add your *arr applications and configure webhooks
5. Set up notification triggers and customize your alerts

## Configuration

Notifiarr stores its configuration in the `/config` directory, which is automatically mapped to your Runtipi app data directory for persistence across container restarts.

For detailed setup instructions and API documentation, visit the [official Notifiarr documentation](https://notifiarr.com/docs/).

## System Integration

This container includes system file mounts for:
- `/var/run/utmp` - User login tracking
- `/etc/machine-id` - System identification

These mounts enable Notifiarr to provide system-level monitoring and notifications.