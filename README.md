# docker-openwrt-r8000

## Build router firmware — customized with OpenWRT ImageBuilder — in Docker.

* Specify build details by editing ENV VARS in the '.env' file.
* Added config and other files in ./files/ DIR according to your desired DIR heirarchy.
* Run `docker compose up`
* Generated images will be found in ./bin/ DIR.
* Flash the image to the router device.

### Untracked DIRs (.gitignore)

* bin/
* files/
