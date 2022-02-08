# [pyunramura/linuxserver-mods_privoxy](https://github.com/pyunramura/linuxserver-mods_privoxy)
**A linuxserver.io container-mod that installs privoxy to securely proxy http/https requests through your container**

[![Release Ship](https://github.com/pyunramura/linuxserver-mods_privoxy/actions/workflows/semver-build-push-release.yaml/badge.svg)](https://github.com/pyunramura/linuxserver-mods_privoxy/actions/workflows/semver-build-push-release.yaml) [![Validate Dockerfile](https://github.com/pyunramura/linuxserver-mods_privoxy/actions/workflows/validate-dockerfile.yaml/badge.svg)](https://github.com/pyunramura/linuxserver-mods_privoxy/actions/workflows/validate-dockerfile.yaml)

This project's home is located at https://github.com/pyunramura/linuxserver-mods_privoxy

Find this image on the Github container registry at [ghcr.io/pyunramura/privoxy](https://github.com/pyunramura/linuxserver-mods_privoxy/pkgs/container/privoxy)

or in the Dockerhub registry at [pyunramura/privoxy](https://hub.docker.com/r/pyunramura/privoxy).

---

## Usage

This config mod is packaged for installation in linuxserver containers by defining:

`-e DOCKER_MODS=pyunramura/privoxy`  or

`-e DOCKER_MODS=ghcr.io/pyunramura/privoxy`

in the container's configuration.

## Constraints

This mod is most useful in conjunction with a linuxserver-based vpn container or a [**docker mod**](https://github.com/pyunramura/linuxserver-mods_wireguard-pia) where privoxy is used to provide anonymous http(s) proxying through the vpn tunnel to other services outside the container.

## Mod Info

The source for this mod was heavily inspired by [hotio/rflood](https://hotio.dev/containers/rflood/)'s implementation.

The mod simply installs [privoxy](http://www.privoxy.org/) proxy within the container and points the application to a default config located at `/config/privoxy/privoxy.conf`.

Be sure to update the port mapping to the container with `-p 8118:8118` in order to access the proxy service.

To change the privoxy listening port within the container, modify the `listen-address :8118` key in `/config/privoxy/privoxy.conf` and map the new internal port accordingly within your container config.
