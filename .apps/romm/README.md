# RomM

[![Docker Pulls](https://img.shields.io/docker/pulls/rommapp/romm?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/rommapp/romm)
[![GitHub Stars](https://img.shields.io/github/stars/rommapp/romm?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/rommapp/romm)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/romm)

## Description

[RomM](https://github.com/rommapp/romm) is a self-hosted ROM manager and player. It scans your game library, enriches it with metadata and artwork from providers such as IGDB and ScreenScraper, and lets you browse, download and play games from the browser.

## Install/Setup

RomM needs a database, so the [MariaDB](../mariadb/README.md) app must be added and running first. DockSTARTer templates cannot declare a dependency on another app, so this is a manual step:

1. Add and start MariaDB (`ds -a mariadb`, set `MYSQL_ROOT_PASSWORD`, then `ds -c`).
1. Create a database and user for RomM (see the SQL below), for example from [phpMyAdmin](../phpmyadmin/README.md) or with `docker exec -it mariadb mysql -uroot -p`.
1. In `.env.app.romm` set `DB_PASSWD` to that password and `ROMM_AUTH_SECRET_KEY` to the output of `openssl rand -hex 32`. `DB_HOST` defaults to `mariadb`, the default MariaDB container name; change it if you renamed the MariaDB container.
1. Add metadata provider credentials (IGDB, ScreenScraper and others) as described in the [RomM documentation](https://docs.romm.app/latest/Getting-Started/Metadata-Providers/).
   Hasheous (ROM identification by file hash) is off by default, as it is upstream. Enabling it sends ROM hashes to the external Hasheous service.

SQL to create the RomM database and user:

```sql
CREATE DATABASE romm;
CREATE USER 'romm-user'@'%' IDENTIFIED BY 'a-strong-password';
GRANT ALL PRIVILEGES ON romm.* TO 'romm-user'@'%';
FLUSH PRIVILEGES;
```

Volumes:

- Your game library is mounted at `/romm/library` from `ROMM__VOLUME_LIBRARY` (default `${DOCKER_VOLUME_STORAGE}/romm/library`). It must follow RomM's [folder structure](https://docs.romm.app/latest/Getting-Started/Folder-Structure/).
- Uploaded saves and states, downloaded artwork, optional `config.yml` and the internal Redis cache are stored under `${DOCKER_VOLUME_CONFIG}/romm`.

RomM runs its own Redis/Valkey inside the container, so no separate cache container is needed.

For general assistance, visit our [support page](https://dockstarter.com/basics/support/).
