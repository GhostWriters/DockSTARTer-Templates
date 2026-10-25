# Wondarr

[![GitHub Stars](https://img.shields.io/github/stars/wulfftech/wondarr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/wulfftech/wondarr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/wondarr)

## Description

[Wondarr](https://wulfftech.github.io/wondarr/) is an \*arr for single songs.
It finds each song you want on Soulseek (slskd is bundled), YouTube Music,
torrents and usenet, checks it is the right recording, tags it and files it
into your music library.

## Install/Setup

`DOCKER_VOLUME_STORAGE` is mounted at `/data`, where Wondarr keeps its library
(`/data/music`) and download folders by default. Your other DockSTARTer apps see
the same folder as `/storage`, so when you add qBittorrent or SABnzbd under
**Settings → Download clients**, add a remote path mapping: path in the client
`/storage`, path Wondarr sees `/data`. The client's **Test** button tells you
when one is missing. With a single mount, torrent imports hard-link instead of
copying.

Forward the Soulseek port (`WONDARR__PORT_50300`, default `50300`) on your
router for better Soulseek results. Keep the host port equal to the container
port: slskd tells the Soulseek network which port it listens on.

Then follow [First run](https://wulfftech.github.io/wondarr/getting-started/first-run/).
If you need assistance setting up this application please visit our
[support page](https://dockstarter.com/basics/support/).
