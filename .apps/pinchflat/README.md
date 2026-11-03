# Pinchflat

[![Docker Pulls](https://img.shields.io/docker/pulls/kieraneglin/pinchflat?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://github.com/kieraneglin/pinchflat/pkgs/container/pinchflat)
[![GitHub Stars](https://img.shields.io/github/stars/kieraneglin/pinchflat?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/kieraneglin/pinchflat)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/pinchflat)

## Description

Pinchflat is a self-hosted app for downloading YouTube content, built on yt-dlp. It automatically checks for and downloads new media from channels or playlists based on user-defined rules, ideal for archiving or integrating with media center applications like Plex or Jellyfin.

## Install/Setup

Pinchflat does not document PUID/PGID environment variables, so the container runs as its own user. Make sure `${DOCKER_VOLUME_CONFIG}/pinchflat` and the downloads folder (`PINCHFLAT__VOLUME_DOWNLOADS`, default `${DOCKER_VOLUME_STORAGE}/downloads/pinchflat`) are writable by it.

Optional HTTP basic auth in front of the web UI can be enabled by setting `BASIC_AUTH_USERNAME` and `BASIC_AUTH_PASSWORD` in `.env.app.pinchflat`; leave both blank to disable it.

For general assistance, visit our [support page](https://dockstarter.com/basics/support/).

## Architecture note

`ghcr.io/kieraneglin/pinchflat` currently publishes only a `linux/amd64` manifest, so this template ships `pinchflat.x86_64.yml` only and the app will not be offered on aarch64 hosts. Add `pinchflat.aarch64.yml` once upstream publishes an arm64 image.
