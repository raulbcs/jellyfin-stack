# Jellyfin Media Stack

This is a media server stack running on Docker with the following services:

## Services Included

1. **Jellyfin** - Media server for streaming movies and TV shows
2. **Sonarr** - TV show management and automation
3. **Radarr** - Movie management and automation
4. **Bazarr** - Subtitle management for Sonarr and Radarr
5. **Prowlarr** - Indexer manager for Sonarr and Radarr
6. **Jackett** - Torrent indexer proxy for Sonarr/Radarr
7. **qBittorrent** - BitTorrent client
8. **Torrent Indexer** - Custom indexer API (submodule, `./torrent-indexer`) backed by Redis
9. **Trawl** - FlareSolverr-compatible browser solver used by Torrent Indexer

## Prerequisites

- Docker
- Docker Compose
- Clone with submodules: `git clone --recurse-submodules https://github.com/raulbcs/jellyfin-stack.git`
  (or run `git submodule update --init` after cloning)

## Service Ports

| Service         | Port |
|-----------------|------|
| Jellyfin        | 8096 |
| Sonarr          | 8989 |
| Radarr          | 7878 |
| Bazarr          | 6767 |
| Prowlarr        | 9696 |
| Jackett         | 9117 |
| qBittorrent     | 8080 |
| Torrent Indexer | 7006 |
| Trawl           | 8191 |

## Configuration

After starting the services, you'll need to configure each service:

1. **Jellyfin**: http://localhost:8096
2. **Sonarr**: http://localhost:8989
3. **Radarr**: http://localhost:7878
4. **Bazarr**: http://localhost:6767
5. **Prowlarr**: http://localhost:9696
6. **Jackett**: http://localhost:9117
7. **qBittorrent**: http://localhost:8080
8. **Torrent Indexer**: http://localhost:7006

## Connecting Services

- Configure Sonarr and Radarr to use qBittorrent as the download client
- Configure Sonarr and Radarr to use correct folder (Media Management > Root Folders)
- Configure Sonarr and Radarr to use Prowlarr as the indexer (or Jackett as an alternative)
- Configure Bazarr to connect to Sonarr and Radarr for subtitles
- Add the Torrent Indexer (http://torrent-indexer:7006) as a custom indexer in Prowlarr/Sonarr/Radarr

## Samsung TV app
- Use [PatrickSt1991/Samsung-Jellyfin-Installer](https://github.com/PatrickSt1991/Samsung-Jellyfin-Installer) to install Jellyfin app in your Samsung TV.
