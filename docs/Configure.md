# Configure

First thing you need to know is that you MUST not use
  **localhost** when configure services connections,
  you should use the name of the container.

Examples:

- When adding Jackett in Sonarr, you MUST not use localhost,
  you MUST use **http://jacket:9117/...**

## Jackett

### Intro

Jackett works as a proxy server: it translates queries from apps (Sonarr,
  Radarr and others) into tracker-site-specific http queries, parses the
  html response, then sends results back to the requesting software

### Setup

Access [http://localhost:9117/](http://localhost:9117/) to add your favorite
  tracker (The Pirate Bay, RARBG, Kick-Ass, ...)

### Documentation

[https://github.com/Jackett/Jackett/wiki](https://github.com/Jackett/Jackett/wiki)

## Sonarr

Sonarr is a PVR for Usenet and BitTorrent users. It can monitor multiple
  RSS feeds for new episodes of your favorite shows and will grab, sort
  and rename them

### Setup

Access [http://localhost:8989/](http://localhost:8989/) to configure it.

- Add all the trackers you configured on Jackett (add only TV categories,
  you can get this information on Jackett)
- Add transmission as your download client
- Add a TV series and Sonarr will ask you for a path, add `/tv`

### Documentation

[https://github.com/Sonarr/Sonarr/wiki](https://github.com/Sonarr/Sonarr/wiki)

## Radarr

Radarr is an independent fork of Sonarr reworked for automatically
  downloading movies via Usenet and BitTorrent.

### Setup

Access [http://localhost:7878/](http://localhost:7878/) to configure it.

- Add all the trackers you configured on Jackett (add only Movie
  categories, you can get this information on Jackett)
- Add transmission as your download client
- Add a Movie and Radarr will ask you for a path, add `/movies`

### Documentation

[https://github.com/Radarr/Radarr/wiki](https://github.com/Radarr/Radarr/wiki)

## Plex

Plex makes it possible to enjoy all of your media, whether in
  your living room, the car, or on a boat in the South Pacific!

### Setup

[http://localhost:32400/web](http://localhost:32400/web)

- Add paths
  - /movies for movies
  - /tv for tv series

### Documentation

[https://support.plex.tv/articles/](https://support.plex.tv/articles/)

### Troubleshoot

If you are having issues with Plex, it's probably because
  of poorly IPv6 support, run the following command to
  fix it.

```bash
sudo -s
sysctl -w net.ipv6.conf.all.disable_ipv6=1
sysctl -w net.ipv6.conf.all.autoconf=0
sysctl -w net.ipv6.conf.default.disable_ipv6=1
sysctl -w net.ipv6.conf.default.autoconf=0
exit
```