# Docker Base Images

This repository builds & publishes my base Docker images that I use across all my other projects.

**I do not recommend that you use these images as base images in your own projects as they are tailored towards my needs!**

## Distributions

These are the Linux distribution images I use the base for all my other images.

The following changes are made on these images:
 * A package repository mirror in the United Kingdom is used.
 * Public CA certificates are installed.
 * My [container healthcheck](https://github.com/viral32111/healthcheck) utility is installed.
 * My [personal CA root certificate](Context/viral32111.crt) is added.
 * A standard user is created.
 * Shell history is disabled.

The following images are available:
* [Ubuntu](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu)
  * 22.10 (`ghcr.io/viral32111/ubuntu:22.10`)
  * 22.04 (`ghcr.io/viral32111/ubuntu:22.04`)
  * 20.04 (`ghcr.io/viral32111/ubuntu:20.04`)
* [Alpine](https://github.com/viral32111/docker-base-images/pkgs/container/alpine)
  * 3.15 (`ghcr.io/viral32111/alpine:3.15`)
  * 3.16 (`ghcr.io/viral32111/alpine:3.16`)
