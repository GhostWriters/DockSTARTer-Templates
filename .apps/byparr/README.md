# Byparr

[![GitHub Stars](https://img.shields.io/github/stars/ThePhaseless/Byparr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/ThePhaseless/Byparr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/byparr)

## Description

[Byparr](https://github.com/ThePhaseless/Byparr) is a self-hosted scraping engine and FastAPI-based service designed as a modern, drop-in replacement for FlareSolverr in the `*arr` stack (such as Prowlarr and Jackett). It utilizes `invisible_playwright` and Camoufox to bypass modern JavaScript challenges and bot protections (such as Cloudflare Turnstile, reCAPTCHA, and hCaptcha).

## Install/Setup

Access the service or configure indexers using:

```text
http://<server-ip>:8191
```

For Prowlarr or Jackett integration, configure Byparr as a FlareSolverr indexer proxy targeting `http://<server-ip>:8191/v1` (or `http://byparr:8191/v1` when on the same Docker bridge network).

## Security

Byparr exposes an unauthenticated HTTP API intended for internal network communication between indexer services and the solver. Do not expose port 8191 directly to the public internet without an authenticating reverse proxy or firewall restriction.
