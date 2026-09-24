# Linkwarden

[![GitHub Container Registry](https://img.shields.io/badge/ghcr.io-linkwarden-607D8B?style=flat-square&logo=github)](https://github.com/linkwarden/linkwarden/pkgs/container/linkwarden)
[![GitHub Stars](https://img.shields.io/github/stars/linkwarden/linkwarden?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/linkwarden/linkwarden)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/linkwarden)

## Description

[Linkwarden](https://linkwarden.app) is a self-hosted collaborative bookmark
manager. Alongside the link it keeps a screenshot, a PDF and a readable copy of
the page, so a bookmark still has its content after the site goes away.

## Install/Setup

This app brings its own PostgreSQL and Meilisearch containers. Three values
have to be set before the first start, each in the file shared with the
container that needs it:

- `NEXTAUTH_SECRET` in `.env.app.linkwarden`, `openssl rand -base64 32`
- `MEILI_MASTER_KEY` in `.env.app.linkwarden-search`, `openssl rand -base64 32`
- `DB_PASSWORD` in `.env.app.linkwarden-database`, the password for the
  companion database

`NEXTAUTH_URL` must be the public URL of the instance with `/api/v1/auth`
appended, for example `https://links.example.com/api/v1/auth`. NextAuth builds
its callback URLs from it, so a mismatch sends every login back to the wrong
host.

Archived pages live in `${DOCKER_VOLUME_CONFIG}/linkwarden/data` and grow with
the number of links.

For single sign on, uncomment the generic OIDC block in the app environment.
The redirect URI to register with the provider is `NEXTAUTH_URL` plus
`/callback/oidc`.

For further configuration see the
[Linkwarden documentation](https://docs.linkwarden.app/self-hosting/environment-variables).
If you need assistance setting up this application please visit our
[support page](https://dockstarter.com/basics/support/).
