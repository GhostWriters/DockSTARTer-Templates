# torrserver

[![GitHub Stars](https://img.shields.io/github/stars/YouROK/TorrServer?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/YouROK/TorrServer)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/torrserver)

## Description

[TorrServer](https://github.com/YouROK/TorrServer) is an application that allows streaming torrent files directly to media players (Kodi, VLC, Android TV, Lampa, etc.) on-the-fly without fully downloading them in advance.

## Install/Setup

Access the web interface at `http://<server-ip>:8090` to manage torrents, adjust cache settings, and view stream links.

## Security

By default, TorrServer operates without authentication (`TS_HTTPAUTH=0`) for ease of use across local network media clients. If accessing TorrServer outside a trusted local network, enable `TS_HTTPAUTH=1` and place the container behind a TLS-terminating reverse proxy (e.g., Nginx Proxy Manager, SWAG, or Traefik) to protect HTTP Basic authentication credentials in transit.
