# Wallos

[![Docker Pulls](https://img.shields.io/docker/pulls/bellamy/wallos?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/bellamy/wallos)
[![GitHub Stars](https://img.shields.io/github/stars/ellite/Wallos?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/ellite/Wallos)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/wallos)

## Description

[Wallos](https://wallosapp.com/) is a self-hosted subscription tracker. It keeps
every recurring payment in one place, converts them to a single currency, shows
what they cost per month or year, and notifies you before one renews.

## Install/Setup

Wallos ships no default account. Open `http://<host>:8282` after the container
starts and the first registration becomes the admin user. Further accounts are
created from Admin, and household members are added under Settings.

Exchange rate conversion needs a free [Fixer](https://fixer.io/#pricing_plan) API
key, entered under Settings. Rates refresh when the main currency changes, so set
the key first, switch currency, then switch back to trigger the first fetch.

Data lives in two folders under the config volume: `db` holds the SQLite database,
`logos` holds uploaded subscription logos and avatars.

## OIDC

OIDC/OAuth login is configured in the Admin UI. It can also be set declaratively
from `.env.app.wallos`, which overrides the stored values at runtime, see the
commented variables in that file. When the identity provider sits on a private or
loopback address, add its host to `SSRF_ALLOWLIST` or Wallos refuses to reach it.
