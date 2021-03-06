# A dockerized Borg server

[![Build Status](https://travis-ci.org/ps1337/borg-docker.png?branch=master)](https://travis-ci.org/ps1337/borg-docker)

This repo contains two variants of a dockerized borg server

- Using a minimal alpine base image (size < 100 MB)
- Using a debian base image

`Dockerfile.debian` is basically just a merged version of these images:

`sebcworks/borgbackup-server` and `sebcworks/borgbackup-base`

which use debian as base image.

The only change is that `borg` gets installed via the latest release from GitHub instead of using pip because otherwise with the missing native msgpack, performance is < 0.

Use `make build` and `make run` to start a dockerized borg instance. Please check the `Makefile` for things you have to configure.
You can also use the built image from docker hub using `docker pull ps1337/borg-docker` which uses the alpine base image.

All credits for the debian Dockerfile go to sebcworks :)
