# Docker Base Images

This repository builds & publishes my base Docker images that I use across all my other projects.

**I do not recommend that you use these images in your own projects as they are tailored towards my needs!**

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
  * 20.04 (`ghcr.io/viral32111/ubuntu:20.04`)
  * 22.04 (`ghcr.io/viral32111/ubuntu:22.04`)
  * 22.10 (`ghcr.io/viral32111/ubuntu:22.10`)
* [Alpine](https://github.com/viral32111/docker-base-images/pkgs/container/alpine)
  * 3.15 (`ghcr.io/viral32111/alpine:3.15`)
  * 3.16 (`ghcr.io/viral32111/alpine:3.16`)

## Java

These images use Java from [Adoptium Temurin](https://adoptium.net/temurin/releases/), and will always use the latest stable version for each major release.

The following images are available:
 * Java 8 (`ghcr.io/viral32111/java:8`)
 * Java 11 (`ghcr.io/viral32111/java:11`)
 * Java 16 (`ghcr.io/viral32111/java:16`)
 * Java 17 (`ghcr.io/viral32111/java:17`)
 * Java 18 (`ghcr.io/viral32111/java:18`)
 * Java 19 (`ghcr.io/viral32111/java:19`)
