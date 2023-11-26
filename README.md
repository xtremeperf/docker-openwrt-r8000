## docker-openwrt-r8000

#### Docker-Compose Frontend for OpenWrt Image Builder

> The OpenWrt Image Builder is a pre-compiled environment suitable for creating custom images without the need for compiling them from source. It downloads pre-compiled packages and integrates them in a single flashable image.

The project in this repository provides a thin Docker wrapper around the OpenWet Image Build to ease firmware image creation, maintenance and version control using the Docker-Compose tool.

#### Build a firmware image for your device

* Edit .env to configure OpenWrt's ImageBuilder options.
* Copy files into the ` files/ ` directory (preserving directory tree structure).
* Run the image build command: ` docker compose up `
* Find the images generated in the ` bin/ ` directory.
* Flash the appropriate device image to your router.

#### Paths ignored by git repo

* ` bin/ `    -- location of new firmware images
* ` files*/ ` -- extra files to merge into firmware image rootfs


