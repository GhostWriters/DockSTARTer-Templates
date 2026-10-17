# Profilarr

[![GitHub Container Registry](https://img.shields.io/badge/ghcr.io-profilarr-607D8B?style=flat-square&logo=github)](https://github.com/Dictionarry-Hub/profilarr/pkgs/container/profilarr)
[![GitHub Stars](https://img.shields.io/github/stars/Dictionarry-Hub/profilarr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/Dictionarry-Hub/profilarr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/profilarr)

## Description

[Profilarr](https://github.com/Dictionarry-Hub/profilarr) manages custom formats and quality profiles for [Radarr](../radarr/README.md) and [Sonarr](../sonarr/README.md). It syncs configurations from version control to any number of Arr instances while preserving local modifications.

## Install/Setup

- Requires Sonarr v4+ and/or Radarr v5+, and a Docker host with kernel 3.17 or newer.
- Profilarr v2 supports `PUID`, `PGID`, `TZ` and `UMASK`, which this template sets.
- Login is on by default. Set `AUTH='off'` in `.env.app.profilarr` only on a trusted network. Set `ORIGIN` if you reach Profilarr through a reverse proxy.
- The optional parser container (`ghcr.io/dictionarry-hub/profilarr-parser`) is only needed for custom format and quality profile testing, and is not included in this template. Linking, syncing and everything else work without it.
- Upstream notes the config database is case-sensitive, so avoid case-insensitive filesystems for the config mount.

For general assistance, visit our [support page](https://dockstarter.com/basics/support/).
