# Media Center

## Introduction

This repository helps you to setup a very good media
  center in an very easy way.

Services included are:

- Jackett
- Sonarr
- Radarr
- Transmission
- Plex

## Setup

The scripts uses the following variables:

```bash
PGID=${PGID:-`id -g`}
PUID=${PUID:-`id -u`}
TZ=${TZ:-"Europe/Brussels"}
DATA=${DATA:-"`pwd`"}
```

**If you don't set they will be choose for you automatically*

Run

```bash
./script/setup
```

## How to run

Run

```bash
./script/server
```

## Update

```bash
./script/update
```

## Configure

[Configure](./docs/Configure.md)
