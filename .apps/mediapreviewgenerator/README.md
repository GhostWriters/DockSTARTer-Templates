# MediaPreviewGenerator

[![Docker Pulls](https://img.shields.io/docker/pulls/stevezzau/media_preview_generator?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/stevezzau/media_preview_generator)
[![GitHub Stars](https://img.shields.io/github/stars/stevezau/media_preview_generator?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/stevezau/media_preview_generator)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/mediapreviewgenerator)

## Description

[MediaPreviewGenerator](https://mediapreviewgenerator.dev/) makes the preview
thumbnails and the Skip Intro and Skip Credits markers for Plex, Emby and
Jellyfin. It starts the moment Sonarr or Radarr imports a file and sends the
results to every server at once.

## Install/Setup

Open the web UI on port `8080` and follow the setup wizard; servers, GPUs,
libraries and schedules are all set there.

- **Signing in:** on first start the app generates a token and saves it in
  `auth.json` in its config folder. Set `WEB_AUTH_TOKEN` to use your own
  instead, or set `AUTH_METHOD` to `external` to turn the built-in sign-in off
  when a reverse proxy or VPN in front of it handles sign-in.
- **Plex data folder:** the container mounts Plex's `Plex Media Server` folder
  as `/plex`, read-write, because Plex keeps preview files inside it. By
  default that's
  `${DOCKER_VOLUME_CONFIG}/plex/Library/Application Support/Plex Media Server`,
  the Plex app's data folder. If your Plex keeps its data elsewhere, change
  `MEDIAPREVIEWGENERATOR__VOLUME_PLEX_DATA`. In the wizard, the Plex Media
  Server data folder is `/plex`.
- **Media:** your storage folders are mounted at the same paths the Plex
  container uses, so the file paths Plex reports work here without path
  mappings.
- **GPU:** set `MEDIAPREVIEWGENERATOR__DEVICES` to `true` to pass
  `/dev/dri` (Intel or AMD) into the container. NVIDIA GPUs need the NVIDIA
  Container Toolkit and an override instead; see the
  [project's docs](https://mediapreviewgenerator.dev/).
