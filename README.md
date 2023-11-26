# docker-openwrt-r8000

## Docker OpenWrt Image Builder for Netgear R8000 routers (and others)

* Edit .env to configure OpenWrt's ImageBuilder options.
* Add your files to the 'files/' DIR (preserve the DIR tree structure).
* Run the image build command: `docker compose up`
* Find build images generated in 'bin/' DIR.
* Flash the correct image to the router device.

## Untracked paths in .gitignore

* bin/
* files/
