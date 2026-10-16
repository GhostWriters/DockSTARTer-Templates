# Cleanuparr

[![GitHub Container Registry](https://img.shields.io/badge/ghcr.io-cleanuparr-607D8B?style=flat-square&logo=github)](https://github.com/Cleanuparr/Cleanuparr/pkgs/container/cleanuparr)
[![GitHub Stars](https://img.shields.io/github/stars/Cleanuparr/Cleanuparr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/Cleanuparr/Cleanuparr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/cleanuparr)

## Description

[Cleanuparr](https://github.com/Cleanuparr/Cleanuparr) automates cleanup of unwanted or blocked downloads for [Sonarr](../sonarr/README.md), [Radarr](../radarr/README.md), [Lidarr](../lidarr/README.md), [Readarr](../readarr/README.md) and [LazyLibrarian](../lazylibrarian/README.md). It blocks known malware and unwanted file types, removes stalled, slow and failed imports, blocklists them in the *arr app and triggers a search for a replacement. It supports qBittorrent, Transmission, Deluge, µTorrent and rTorrent.

## Install/Setup

- All configuration (download clients, *arr apps, Malware Blocker, Queue Cleaner, Download Cleaner) is done in the web UI on port `11011`.
- So that blocked releases are not grabbed again, enable `Sync Reject Blocklisted Torrent Hashes While Grabbing` for each app in Prowlarr (`Settings` > `Apps`, advanced settings), or `Reject Blocklisted Torrent Hashes While Grabbing` on each indexer in the *arr apps if you do not use Prowlarr. See the [prerequisites](https://cleanuparr.github.io/Cleanuparr/docs/installation/).
- The Download Cleaner's orphan and hardlink checks need the download client's paths at the same location inside Cleanuparr. Keep `CLEANUPARR__STORAGE_ON` enabled if your downloads live under `/storage`.

For general assistance, visit our [support page](https://dockstarter.com/basics/support/).
