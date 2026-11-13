# Samba

[![Docker Pulls](https://img.shields.io/docker/pulls/adrianmusante/samba?style=flat-square&color=607D8B&label=docker%20pulls&logo=docker)](https://hub.docker.com/r/adrianmusante/samba)
[![GitHub Stars](https://img.shields.io/github/stars/adrianmusante/docker-samba?style=flat-square&color=607D8B&label=github%20stars&logo=github)](https://github.com/adrianmusante/docker-samba)
[![Compose Templates](https://img.shields.io/static/v1?style=flat-square&color=607D8B&label=compose&message=templates)](https://github.com/GhostWriters/DockSTARTer-Templates/tree/main/.apps/samba)

## Description

Since 1992, [Samba](https://www.samba.org/) has provided secure, stable and
fast file and print services for all clients using the SMB/CIFS protocol, such
as all versions of DOS and Windows, OS/2, Linux and many others.

This template uses
[adrianmusante/samba](https://github.com/adrianmusante/docker-samba), an
updated version of the Samba Docker image, originally developed by
[dperson/samba](https://github.com/dperson/samba).

By default, Samba will share all media directories and
[Docker config directory](https://dockstarter.com/basics/env-var-info/#DOCKER_VOLUME_CONFIG)
over SMB on the host. All of these directories will be placed inside whatever
share name is specified for `SAMBA__ENVIRONMENT_SHARENAME` in your `.env` file.
These shares are protected with username `ds` and password `ds` by default, but
**can and should be** changed in your `.env` file.

## Install/Setup

This application does not have any specific setup instructions documented. If
you need assistance setting up this application please visit our
[support page](https://dockstarter.com/basics/support/).

### Access Shares

Replace `host` with your DNS or IP-address of your Docker host.

- `\\host\DockSTARTer`

### Network Discovery

`SAMBA_NMBD` in `.env.app.samba` starts the `nmbd` daemon to advertise the
shares. Any non-empty value enables it; leave it blank to disable it. There are
reports that `nmbd` only works if the container uses the host's network stack
(set `SAMBA__NETWORK_MODE` to `host` in your `.env` file).

### Setting Up Additional Shares

You can set up additional shares using an
[override](https://dockstarter.com/overrides/introduction/). Each extra share
needs a `SAMBA_SHAREx` environment variable (`SAMBA_SHARE2`, `SAMBA_SHARE3`,
...) in the format
`<name>;</path>[;browse;readonly;guest;users;admins;writelist;comment]`, and a
volume mounting the host folder at that path:

```yaml
services:
  samba:
    environment:
      - SAMBA_SHARE2=AnotherShare;/AnotherShare;yes;no;no;all;${SAMBA__ENVIRONMENT_USERNAME?}
    volumes:
      - /path/to/your/share:/AnotherShare
```

Run `ds -c up samba` to recreate the container with the new share.

#### How To Mount Windows Share in Linux

See [SMB Mounting](https://dockstarter.com/advanced/smb-mounting/).
