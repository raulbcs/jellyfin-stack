# Jellyfin Media Stack

This is a media server stack running on Docker with the following services:

## Services Included

1. **Jellyfin** - Media server for streaming movies and TV shows
2. **Sonarr** - TV show management and automation
3. **Radarr** - Movie management and automation
4. **Prowlarr** - Indexer manager for Sonarr and Radarr
5. **Jackett** - Torrent indexer proxy for Sonarr/Radarr
6. **qBittorrent** - BitTorrent client

## Prerequisites

- Docker
- Docker Compose

## Service Ports

| Service      | Port  |
|--------------|-------|
| Jellyfin     | 8096  |
| Sonarr       | 8989  |
| Radarr       | 7878  |
| Prowlarr     | 9696  |
| Jackett      | 9117  |
| qBittorrent  | 8080  |

## Configuration

After starting the services, you'll need to configure each service:

1. **Jellyfin**: http://localhost:8096
2. **Sonarr**: http://localhost:8989
3. **Radarr**: http://localhost:7878
4. **Prowlarr**: http://localhost:9696
5. **Jackett**: http://localhost:9117
6. **qBittorrent**: http://localhost:8080

## Connecting Services

- Configure Sonarr and Radarr to use qBittorrent as the download client
- Configure Sonarr and Radarr to use correct folder (Media Management > Root Folders)
- Configure Sonarr and Radarr to use Prowlarr as the indexer (or Jackett as an alternative)

## Samsung TV app
- Use [PatrickSt1991/Samsung-Jellyfin-Installer](https://github.com/PatrickSt1991/Samsung-Jellyfin-Installer) to install Jellyfin app in your Samsung TV.