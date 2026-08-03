# Cloudflared

[![Docker Pulls](https://img.shields.io/docker/pulls/cloudflare/cloudflared?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/cloudflare/cloudflared)
[![GitHub Stars](https://img.shields.io/github/stars/cloudflare/cloudflared?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/cloudflare/cloudflared)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/cloudflared)

## Description

[Cloudflared](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)
is the Cloudflare Tunnel client. It creates an outbound-only connection to
Cloudflare's network so you can expose private services to the internet
without opening ports on your firewall.

## Install/Setup

Set `TUNNEL_TOKEN` in the app environment to the tunnel token from the
Cloudflare Zero Trust dashboard (Networks → Tunnels). The token authenticates
this connector to your Cloudflare account, and the routes to your services
are configured in that dashboard rather than in DockSTARTer.
