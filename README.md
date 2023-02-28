# Alpine build of Deluge BitTorrent Client

This repository builds the source code of [Deluge BitTorrent Client](https://github.com/deluge-torrent/deluge)
into Alpine/Edge packages (see releases) that will be used to serve Deluge in Alpine Docker containers.
Before building, we made some small changes that are **NOT** appropriate to submit to the upstream repo:

- **Allow hacking User-agent**: Because some PT sites don't support version 2.x.x, we had to modify the user-agent and peer-id accordingly.   

- **Allow removing login for web UI**: Since this package is intended to be use in a Docker container, login is not necessary (at least for me personally).

If that's not the case for you, please consider use [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge) docker images.

### Used the docker image

    docker pull dzhuang/docker-deluge:latest

Please navigate [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge) to see on how to use the image.


### User-agent and peer-id of known clients

| Name | User-agent | Peer-id |
|------|------------|---------|
|utorrentMac 1.6.4| uTorrentMac/1640(27255)| -UM1640-|
|utorrent 2.2.1 |uTorrent/2210(25110)| -UT2210-|
|Transmission 2.11| Transmission/2.11| -TR2110-|
|Deluge 1.3.5| Deluge/1350| -DE1350-|

Ref: [Make Your PeerID Your Choice.](https://www.sb-innovation.de/showthread.php?29320-Make-Your-PeerID-Your-Choice)

### Changelog
- deluge-2.1.1r6
    - Allow usings options to set agent version and peer_id, via `Preferences` -> `Other` -> `Custom Deluge Agent`
    - Allow turning off web UI auth (no password login), via options via `Preferences` -> `Interface` -> `Skip Auth`. Use this at you own risk.

- deluge-2.1.1r1
    - Package: Version hack to 1.3.15 and removed web UI login
    - Docker image: Added YARSS2 plugin
