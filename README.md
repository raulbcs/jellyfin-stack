# Jellyfin Media Stack

This is a media server stack running on Docker with the following services:

## Services Included

1. **Jellyfin** - Media server for streaming movies and TV shows
2. **Sonarr** - TV show management and automation
3. **Prowlarr** - Indexer manager for Sonarr
4. **Jackett** - Torrent indexer proxy for Sonarr/Radarr
5. **qBittorrent** - BitTorrent client

## Directory Structure

```
.
├── config/          # Configuration files for all services
├── media/           # Media files (movies and TV shows)
├── downloads/       # Downloaded files (movies and TV shows)
├── docker-compose.yml
└── .env
```

## Prerequisites

- Docker
- Docker Compose

## Installation

1. Clone this repository:
   ```bash
   git clone git@github.com:raulbcs/jellyfin-stack.git
   cd jellyfin-stack
   ```

2. Create the directory structure:
   ```bash
   mkdir -p media/tv downloads/tv
   ```

3. Start the services:
   ```bash
   docker-compose up -d
   ```

## Service Ports

| Service      | Port  |
|--------------|-------|
| Jellyfin     | 8096  |
| Sonarr       | 8989  |
| Prowlarr     | 9696  |
| Jackett      | 9117  |
| qBittorrent  | 8080  |

## Configuration

After starting the services, you'll need to configure each service:

1. **Jellyfin**: http://localhost:8096
2. **Sonarr**: http://localhost:8989
3. **Prowlarr**: http://localhost:9696
4. **Jackett**: http://localhost:9117
5. **qBittorrent**: http://localhost:8080

## Connecting Services

- Configure Sonarr to use qBittorrent as the download client
- Configure Sonarr to use correct folder (Media Management > Root Folders)
- Configure Sonarr to use Prowlarr as the indexer (or Jackett as an alternative)
- Configure Sonarr to hardlink files

## Managing the Stack

- Start all services: `docker-compose up -d`
- Stop all services: `docker-compose down`
- View logs: `docker-compose logs -f <service_name>`
- Update services: `docker-compose pull && docker-compose up -d`

## Notes
- Configuration files are persisted in the `config` directory
- Media files are stored in the `media` directory (copied by Radarr/Sonarr)
- Downloaded files are stored in the `downloads` directory