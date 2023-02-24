# Alpine build of Deluge BitTorrent Client

This repository builds the source code of [Deluge BitTorrent Client](https://github.com/deluge-torrent/deluge)
into Alpine/Edge packages (see releases) that will be used to serve Deluge in Alpine Docker containers.
Before building, we made some small changes that are **NOT** appropriate to submit to the upstream repo:

- **Version hack**: Because some PT sites don't support version 2.x.x, we had to modify the version number back to 1.3.15.   

- **Removed login for web UI**: Since this package is intended to be use in a Docker container, login is not necessary (at least for me personally).

If that's not the case for you, please consider use [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge) docker images.

### Used the docker image

    docker pull dzhuang/docker-deluge:latest

Please navigate [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge) to see on how to use the image.


### Changelog
- deluge-2.1.1r1
    - Package: Version hack to 1.3.15 and removed web UI login
    - Docker image: Added YARSS2 plugin
