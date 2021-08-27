# Ansible NAS

This is my personal fork of [Ansible NAS](https://github.com/davestephens/ansible-nas)
I am working on it for my own benefit and wanted to share with others what apps/changes I've made. I will only be updating documentation for the apps that I have used/worked on. Please let me know if there is an app that isn't working or that needs improved documentation.

### Available Applications

# Front Pages

* [Heimdall](https://heimdall.site/) - Home server dashboard
* [Organizr](https://organizr.app/) - ORGANIZR aims to be your one stop shop for your Servers Frontend.

# Dashboards

* [Glances](https://nicolargo.github.io/glances/) - for seeing the state of your system via a web browser
* [Grafana](https://github.com/grafana/grafana) - Dashboarding tool
* [Netdata](https://my-netdata.io/) - An extremely comprehensive system monitoring solution
* [Portainer](https://portainer.io/) - for managing Docker and running custom images
* [Tautulli](http://tautulli.com/) - Monitor Your Plex Media Server

# Media Downloaders

* [Deluge](https://dev.deluge-torrent.org/) - A lightweight, Free Software, cross-platform BitTorrent client.
* [NZBget](https://nzbget.net/) - The most efficient usenet downloader
* [Transmission](https://transmissionbt.com/) - BitTorrent client (with OpenVPN if you have a supported VPN provider)
* [uTorrent](https://www.utorrent.com/) - The best torrent downloading app for beginners

# Media Source Aggregators

* [Jackett](https://github.com/Jackett/Jackett) - API Support for your favorite torrent trackers

# Media Aggregators

* [Bazarr](https://github.com/morpheus65535/bazarr) - companion to Radarr and Sonarr for downloading subtitles
* [Calibre-web](https://github.com/janeczku/calibre-web) - Provides a clean interface for browsing, reading and downloading eBooks using an existing Calibre database.
* [Lidarr](https://github.com/lidarr/Lidarr) - Music collection manager for Usenet and BitTorrent users
* [Mylar](https://github.com/evilhero/mylar) - An automated Comic Book downloader (cbr/cbz) for use with SABnzbd, NZBGet and torrents
* [Ombi](https://ombi.io/) - web application that gives your users the ability to request content
* [Radarr](https://radarr.video/) - for organising and downloading movies
* [Sickchill](https://sickchill.github.io/) - for managing TV episodes
* [Sonarr](https://sonarr.tv/) - for downloading and managing TV episodes
* [YouTubeDL-Material](https://github.com/Tzahi12345/YoutubeDL-Material) - Self-hosted YouTube downloader built on Material Design

# Media Browsers

* [Airsonic](https://airsonic.github.io/) - catalog and stream music
* [Emby](https://emby.media/) - Media streaming and management
* [Jellyfin](https://jellyfin.github.io) - The Free Software Media System
* [MyMediaForAlexa](https://www.mymediaalexa.com/) - Lets you stream your music collection to your alexa device
* [Plex](https://www.plex.tv/) - Plex Media Server
* [Ubooquity](http://vaemendis.net/ubooquity/) - Book and comic server

# Git

* [GitLab](https://about.gitlab.com/features/) - Self-hosted GitHub clone of the highest order

# Server Operations

* [InfluxDB](https://github.com/influxdata/influxdb) - Time series database used for stats collection
* [Mosquitto](https://mosquitto.org) - An open source MQTT broker
* [Telegraf](https://github.com/influxdata/telegraf) - Metrics collection agent
* [Watchtower](https://github.com/v2tec/watchtower) - Monitor your Docker containers and update them if a new version is available

# Misc

* [Bitwarden_rs](https://github.com/dani-garcia/bitwarden_rs) - Self-Hosting port of password manager
* [Cloudflare DDNS](https://hub.docker.com/r/joshuaavalon/cloudflare-ddns/) - automatically update Cloudflare with your IP address
* [Duplicati](https://www.duplicati.com/) - for backing up your stuff
* [Home Assistant](https://www.home-assistant.io) - Open source home automation
* [Nextcloud](https://nextcloud.com/) - A self-hosted Dropbox alternative
* [Traefik](https://traefik.io/) - Web proxy and SSL certificate manager. Lets you access your services via domain (e.g: plex.domain.net, heimdall.domain.net)


## What This Could Do

Ansible-NAS can run anything that's in a Docker image, which is why Portainer is
included. A NAS configuration is a pretty personal thing based on what you
download, what media you view, how many photos you take...so it's difficult to
please everyone.

That said, if specific functionality you want isn't included and you think
others could benefit, add it and raise a PR!

## What This Doesn't Do

Ansible NAS doesn't set up your disk partitions, primarily because getting it wrong can be incredibly destructive.
That aside, configuring partitions is usually a one-time (or very infrequent) event, so there's not much to be
gained by automating it. Check out the [docs](https://davestephens.github.io/ansible-nas) for recommended setups.

## Installation

See [Installation](https://davestephens.github.io/ansible-nas/installation/).

## Upgrading

**The way Ansible-NAS configuration is structured has changed!** See [Upgrading](https://davestephens.github.io/ansible-nas/upgrading/) for more information. See the **Getting Help** section if you get stuck.

## Documentation

You can read the docs [here](https://davestephens.github.io/ansible-nas). PRs
for more documentation always welcome!

## Migrating from FreeNAS

Assuming that your Ubuntu system disk is separate from your storage (it should be!):

1. Ensure you have a working backup of your data.
2. Check that the working backup you think you have actually works.
3. SSH to the server and run `zpool list` to determine available ZFS pools.
4. `zpool import <pool_name>` against each of the pools you want to attach.
5. `chown -R root:root /mnt/<pool_name>` to fix the ownership of the data.
6. Follow the Quick Start instructions above.

## Requirements

* Ansible NAS targets the latest Ubuntu LTS release, which is currently Ubuntu
  Server 20.04 LTS.
* You can run Ansible-NAS on whatever you like, read the docs for more info. I
  use an HP Microserver.

## Getting Help

Getting help is easy! You can:

* Read the [docs](https://davestephens.github.io/ansible-nas)
* Start a [discussion](https://github.com/davestephens/ansible-nas/discussions)
* Raise an [issue](https://github.com/davestephens/ansible-nas/issues) if you think you've found a bug
* Chat on [Gitter](https://gitter.im/Ansible-NAS/Chat)

## Contributing

Contributions are always welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## Support

If you've enjoyed Ansible-NAS as much as I do working on it, please consider [buying me a coffee](https://ko-fi.com/davestephens) :coffee:

## Thanks

Thanks to the awesome dudes at [JetBrains](https://www.jetbrains.com/?from=Ansible-NAS) for supplying core contributors with JetBrains Open Source licenses!
