# autopulse

[![Docker Pulls](https://img.shields.io/docker/pulls/danonline/autopulse?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/danonline/autopulse)
[![GitHub Stars](https://img.shields.io/github/stars/dan-online/autopulse?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/dan-online/autopulse)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/autopulse)

## Description

[autopulse](https://autopulse.dancodes.online/) is a web server that receives
notifications from media organizers like Sonarr/Radarr/Lidarr/etc and updates
the items in media servers like Plex/Jellyfin/Emby/etc. It is designed to be
efficient, only updating the items that have changed, reducing the load on
media servers.

## Install/Setup

autopulse requires a configuration file to run. Create `config.yml` (or
`config.toml`, `config.yaml` or `config.json`) in the app's config folder,
`${DOCKER_VOLUME_CONFIG}/autopulse`, which the container mounts as `/app`. See
the [project's docs](https://autopulse.dancodes.online/) for the triggers,
targets and path rewrites it can hold.

- **Signing in:** the web UI and webhooks use basic auth. Without an `auth`
  section in the config file the sign-in is `admin` / `password`; set your
  own `username` and `password` there before exposing the app.
- **Webhooks:** in Sonarr, Radarr and the like, add a Webhook connection
  pointing at `http://<host>:2875/triggers/<trigger>`, where `<trigger>` is
  the trigger's name in the config file, with the same sign-in.
- **Database:** the template uses the `latest-sqlite` image and keeps the
  database at `data/autopulse.db` in the config folder.
- **Web UI:** served at `/ui/` on port `2875`, where you can browse scan
  events, retry failures, view the config and submit manual scans.
- **Media:** your storage folders are mounted at the same paths your other
  containers use, so autopulse's file checks find the files Sonarr and Radarr
  report.
