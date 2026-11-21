# Byparr

[![GitHub Stars](https://img.shields.io/github/stars/ThePhaseless/Byparr?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/ThePhaseless/Byparr)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/byparr)

## Description

[Byparr](https://github.com/ThePhaseless/Byparr) is a self-hosted scraping engine and FastAPI-based service designed as a modern, drop-in replacement for FlareSolverr in the `*arr` stack (such as Prowlarr and Jackett). It utilizes `invisible_playwright` and Camoufox to bypass modern JavaScript challenges and bot protections (such as Cloudflare Turnstile, reCAPTCHA, and hCaptcha).

## Install/Setup

Access the service locally or configure indexers using:

```text
http://127.0.0.1:8191
```

For Prowlarr or Jackett running on the same host or within the Docker bridge network, configure Byparr as a FlareSolverr indexer proxy targeting `http://byparr:8191/v1` (internal container networking) or `http://127.0.0.1:8191/v1` (from the local host).

## Security

Byparr exposes an unauthenticated API that instructs a headless browser to retrieve arbitrary URLs. To prevent Server-Side Request Forgery (SSRF) and abuse by unauthenticated network callers, the default port mapping binds strictly to loopback (`127.0.0.1`). If you need to access Byparr from outside the local machine, place it behind an authenticating reverse proxy (such as Nginx, Traefik, or Authelia/Authentik) or restrict network access using a firewall (such as UFW) rather than exposing the port to all interfaces.
