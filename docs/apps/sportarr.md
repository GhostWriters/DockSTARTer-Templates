# Sportarr

[![Docker Pulls](https://img.shields.io/docker/pulls/sportarr/sportarr?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/sportarr/sportarr)
[![GitHub Stars](https://img.shields.io/github/stars/Sportarr/Sportarr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/Sportarr/Sportarr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/sportarr)

## Description

[Sportarr](https://sportarr.net/) is a PVR for sports events. It works like
the other *arr apps, but for sports. It monitors the leagues and events you
follow, grabs releases from your indexers via Usenet and BitTorrent, and
sorts and renames them into a library that Plex, Emby, Jellyfin, and Kodi
understand as seasons and episodes.

## Install/Setup

The web UI listens on port `1867`. On first run, open it and complete the
setup wizard, then add your leagues and point your library folders at paths
under `/storage`.

Sportarr uses its own SQLite database inside `/config` by default, so no
database setup is needed. To use PostgreSQL instead, set
`Sportarr__Database__Provider` to `postgres` in the app environment and fill
in the `Sportarr__Database__*` connection settings (the DockSTARTer `postgres`
app works for this). Any other value, including blank, uses SQLite and the
remaining database settings are ignored. PostgreSQL is supported for fresh
installs only; there is no migration path from an existing SQLite database.

For indexers, connect Sportarr to Prowlarr using Prowlarr's standard *arr
application sync. Further documentation is available on the
[Sportarr wiki](https://wiki.sportarr.net/).
