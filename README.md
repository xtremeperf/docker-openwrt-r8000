## docker-openwrt-r8000

#### Docker-Compose Frontend for OpenWrt Image Builder

> The OpenWrt Image Builder is a pre-compiled environment suitable for creating custom images without the need for compiling them from source. It downloads pre-compiled packages and integrates them in a single flashable image.

The project in this repository provides a thin Docker wrapper around the OpenWrt Image Build to ease firmware image creation, maintenance and version control using the Docker-Compose tool.

#### Build firmware image for your device:

* Create a `.env` file (for setting build options) by making a copy of the included `sample.env` file.
```sh
        sh -c 'mv sample.env .env'
```
* Edit the `.env` file to set build options to be used for creating a new OpenWrt firmware image.
```sh
        sh -c 'editor .env'
```
* OPTIONAL: to add custom files to new OpenWrt firmware image during build time, copy them to `files/` (keep DIR hierarchy consistant with OpenWrt root)
```sh
        sh -c 'mkdir -P files/etc/config'
        sh -c "cp <FILENAME> files/etc/config/"
```
* Run Docker Compose to create a new OpenWrt firmware image using build options from `.env` file.
```sh
        sh -c 'docker compose up'
```
* Successful builds store the new firmware image(s) in `bin/`.
* Flash the appropriate firmware image to your router device.

#### Flash generated firmware image to your device:

* Copy generated firmware image to the router.
```sh
        sh -c 'scp -O bin/<FILENAME>.chk <HOSTNAME>:/tmp/'
```
* Login to the router using SSH (secure shell) and flash using sysupgrade.
```sh
        sh -c 'sysupgrade /tmp/<FILENAME>.chk
```


