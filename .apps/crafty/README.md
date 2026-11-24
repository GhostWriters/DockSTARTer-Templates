# crafty

[![Docker Pulls](https://img.shields.io/docker/pulls/arcadiatechnology/crafty-4?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/arcadiatechnology/crafty-4)
[![GitHub Stars](https://img.shields.io/gitlab/stars/crafty-controller%2Fcrafty-4?style=flat-square&color=607D8B&label=gitlab%20stars&logo=gitlab)](https://gitlab.com/crafty-controller/crafty-4)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/crafty)

## Description

[Crafty Controller](https://craftycontrol.com/) is a next-generation web-based control panel for launching, monitoring, and administering Minecraft Java and Bedrock dedicated servers.

## Install/Setup

Access the web interface over HTTPS at `https://<server-ip>:8443`.

On first launch, check the container logs to retrieve the generated default administrator credentials:

```bash
docker logs <container_name>
```

*(Replace `<container_name>` with your configured container name, e.g. `docker logs crafty`)*.
