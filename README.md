# Jellyfin Media Stack

This is a complete media server stack running on Docker with the following services:

## Services Included

1. **Jellyfin** - Media server for streaming movies and TV shows
2. **Radarr** - Movie management and automation
3. **Sonarr** - TV show management and automation
4. **Prowlarr** - Indexer manager for Radarr and Sonarr
5. **Jellyseerr** - Request management and monitoring for Jellyfin
6. **qBittorrent** - BitTorrent client
7. **Bazarr** - Subtitle management for movies and TV shows
8. **Dozzle** - Used to view the logs of any container
9. **Homarr** - Used as a dashboard for docker containers
10. **Janitorr** - Removes untagged media when it reaches a certain age
11. **Jackett** - Additional indexer support

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
   mkdir -p media/movies media/tv downloads/movies downloads/tv
   ```

3. Start the services:
   ```bash
   docker-compose up -d
   ```

## Service Ports

| Service      | Port  |
|--------------|-------|
| Jellyfin     | 8096  |
| Radarr       | 7878  |
| Sonarr       | 8989  |
| Prowlarr     | 9696  |
| Jackett      | 9117  |
| Jellyseerr   | 5055  |
| qBittorrent  | 8080  |
| Bazarr       | 6767  |
| Dozzle       | 9999  |
| Homarr       | 7575  |
| Janitorr     | 8978  |

## Configuration

After starting the services, you'll need to configure each service:

1. **Jellyfin**: http://localhost:8096
2. **Radarr**: http://localhost:7878
3. **Sonarr**: http://localhost:8989
4. **Prowlarr**: http://localhost:9696
5. **Jackett**: http://localhost:9117
6. **Jellyseerr**: http://localhost:5055
7. **qBittorrent**: http://localhost:8080
8. **Bazarr**: http://localhost:6767
9. **Dozzle**: http://localhost:9999
10. **Homarr**: http://localhost:7575

## Connecting Services

- Configure Radarr and Sonarr to use qBittorrent as the download client
- Configure Radarr and Sonarr to use Prowlarr as the indexer
- Configure Jellyseerr to connect to Jellyfin
- Configure Bazarr to connect to Radarr and Sonarr

## Managing the Stack

- Start all services: `docker-compose up -d`
- Stop all services: `docker-compose down`
- View logs: `docker-compose logs -f <service_name>`
- Update services: `docker-compose pull && docker-compose up -d`

## Notes

- All services are configured to restart automatically unless stopped
- Configuration files are persisted in the `config` directory
- Media files are stored in the `media` directory
- Downloaded files are stored in the `downloads` directory
- The stack is optimized for M1 Mac hardware acceleration
