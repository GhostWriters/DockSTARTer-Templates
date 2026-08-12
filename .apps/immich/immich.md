# Immich

[![GitHub Container Registry](https://img.shields.io/badge/ghcr.io-immich--server-607D8B?style=flat-square&logo=github)](https://github.com/immich-app/immich/pkgs/container/immich-server)
[![GitHub Stars](https://img.shields.io/github/stars/immich-app/immich?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/immich-app/immich)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/immich)

## Description

[Immich](https://immich.app/) is a self-hosted photo and video management
solution that allows you to back up, organize, and browse your photos and
videos with ease, without sacrificing your privacy.

## Install/Setup

This app includes all required services (server, machine learning, PostgreSQL
with pgvecto.rs, and Valkey/Redis). Make sure to set a strong password for both
`DB_PASSWORD` and `POSTGRES_PASSWORD` in the app environment, and ensure they
match.
