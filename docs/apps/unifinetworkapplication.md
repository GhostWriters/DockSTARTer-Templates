# UniFi Network Application

[![Docker Pulls](https://img.shields.io/docker/pulls/linuxserver/unifi-network-application?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/linuxserver/unifi-network-application)
[![GitHub Stars](https://img.shields.io/github/stars/linuxserver/docker-unifi-network-application?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/linuxserver/docker-unifi-network-application)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/unifinetworkapplication)

## Description

The [UniFi Network Application](https://ui.com/) is Ubiquiti's software for
managing UniFi network devices such as access points, switches, and gateways
from a web UI.

## Install/Setup

This app includes the required MongoDB service. Make sure to set a strong
password for `MONGO_PASS` in the app environment before starting it. The web
UI is served over HTTPS on port 8443.
