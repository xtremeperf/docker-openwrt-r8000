## docker-openwrt-r8000

#### Docker OpenWrt Image Builder for Netgear R8000 routers (and others)

* Edit .env to configure OpenWrt's ImageBuilder options.
* Copy files into the `files/` directory (preserving directory tree structure).
* Run the image build command: `docker compose up`
* Find the images generated in the `bin/` directory.
* Flash the appropriate device image to your router.

#### Untracked paths in `.gitignore`

* bin/
* files/
