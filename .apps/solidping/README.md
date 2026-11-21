# SolidPing

[![Docker Pulls](https://img.shields.io/docker/pulls/fclairamb/solidping?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/fclairamb/solidping)
[![GitHub Stars](https://img.shields.io/github/stars/fclairamb/solidping?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/fclairamb/solidping)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/solidping)

## Description

[SolidPing](https://www.solidping.io/) is a self-hosted uptime monitoring server. It checks HTTP, DNS, TCP, ICMP, TLS certificates, databases, message brokers and cron job heartbeats, sends alerts to email, Slack, Discord, Telegram or webhooks, and serves public status pages.

## Install/Setup

The web interface listens on port `4000`. The first login is `admin@solidping.io` / `solidpass` in the `default` organization, and SolidPing asks you to change the password right away.

Data is stored in a SQLite database in `/data`, mapped to `${DOCKER_VOLUME_CONFIG}/solidping`. The container runs as `${PUID}:${PGID}`, so that folder must be writable by that user.

If you reach SolidPing through a reverse proxy, set `SP_BASE_URL` in `.env.app.solidping` to the public URL, so links in notifications point to the right place.

The full list of settings is in the [documentation](https://docs.solidping.io/configuration/).
