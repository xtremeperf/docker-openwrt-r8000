## docker-openwrt-r8000

#### Docker-Compose Frontend for OpenWrt Image Builder

> The OpenWrt Image Builder is a pre-compiled environment suitable for creating custom images without the need for compiling them from source. It downloads pre-compiled packages and integrates them in a single flashable image.

The project in this repository provides a thin Docker wrapper around the OpenWrt Image Build to ease firmware image creation, maintenance and version control using the Docker-Compose tool.

#### Build firmware image for your device:

* Create a new `.env` file by making a copy of the `sample.env` file.
```sh
        sh -c 'mv sample.env .env'
```
* Edit `.env` and save build options for new firware image.
```sh
        sh -c 'editor .env'
```
* OPTIONAL: to add files, copy to `files/` DIR (keep path structure relative to OpenWrt root)
```sh
        sh -c 'mkdir -P files/etc/config'
        sh -c "cp <FILENAME> files/etc/config/"
```
* Run `docker-compose` to build firmware image using options from `.env` file.
```sh
        sh -c 'docker compose up'
```
* Upon successful build the firmware image(s) are stored be in `bin/` DIR.
* Flash the appropriate device image to your router.

#### Flash generated firmware image to your device:

* Copy generated firmware image to the router.
```sh
        sh -c 'scp -O bin/<FILENAME>.chk <HOSTNAME>:/tmp/'
```
* Login to the router using SSH (secure shell) and flash using sysupgrade.
```sh
        sh -c 'sysupgrade /tmp/<FILENAME>.chk
```


