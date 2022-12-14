# Docker Base Images

This repository builds & publishes my base Docker images that I use across all my other projects.

**I do not recommend that you use these images in your own projects as they are tailored towards my needs!**

## Distributions

These are the Linux distribution images I use the base for all my other images.

These images are built from root filesystem tarballs, and will always use the latest stable version for each major release.

The following changes have been made within these images:
 * Switched to a package repository mirror in the United Kingdom.
 * Installed public CA certificates & my [personal root CA certificate](Context/viral32111.crt).
 * Installed my [container healthcheck](https://github.com/viral32111/healthcheck) utility.
 * Created a standard, unprivileged user & group (UID & GID: `1000`).
 * Disabled writing shell history to file.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Ubuntu 20.04](https://www.releases.ubuntu.com/focal/) | 20.04.5 | [`ghcr.io/viral32111/ubuntu:20.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 22.04](https://www.releases.ubuntu.com/jammy/) | 22.04.1 | [`ghcr.io/viral32111/ubuntu:22.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 22.10](https://www.releases.ubuntu.com/kinetic/) | 22.10 | [`ghcr.io/viral32111/ubuntu:22.10`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| ~~[Alpine Linux 3.15](https://alpinelinux.org/)~~ | ~~3.15.6~~ | ~~[`ghcr.io/viral32111/alpine:3.15`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine)~~ | Deprecated. |
| [Alpine Linux 3.16](https://alpinelinux.org/) | 3.16.3 | [`ghcr.io/viral32111/alpine:3.16`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.17](https://alpinelinux.org/) | 3.17.0 | [`ghcr.io/viral32111/alpine:3.17`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |

## Java

These images use Java from [Adoptium Temurin](https://adoptium.net/temurin/releases/), and will always use the latest stable version for each major release.

These images are based on Alpine Linux 3.17.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Java 8](https://adoptium.net) | 8u352-b08 | [`ghcr.io/viral32111/java:8`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 11](https://adoptium.net) | 11.0.17+8 | [`ghcr.io/viral32111/java:11`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 16](https://adoptium.net) | 16.0.2+7 | [`ghcr.io/viral32111/java:16`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | Uses JDK instead of JRE. |
| [Java 17](https://adoptium.net) | 17.0.5+8 | [`ghcr.io/viral32111/java:17`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 18](https://adoptium.net) | 18.0.2.1+1 | [`ghcr.io/viral32111/java:18`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 19](https://adoptium.net) | 19.0.1+10 | [`ghcr.io/viral32111/java:19`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |

## .NET

These images are based on Alpine Linux 3.17.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [.NET Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.11 | [`ghcr.io/viral32111/dotnet:6.0`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |
| [.NET Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.0 | [`ghcr.io/viral32111/dotnet:7.0`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [ASP.NET Core Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.11 | [`ghcr.io/viral32111/aspnetcore:6.0`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |
| [ASP.NET Core Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.0 | [`ghcr.io/viral32111/aspnetcore:7.0`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |

## Node.js

These images are based on Ubuntu 22.10.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Node.js v18](https://nodejs.org) | 18.12.1 | [`ghcr.io/viral32111/nodejs:18`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | |
| [Node.js v19](https://nodejs.org) | 19.2.0 | [`ghcr.io/viral32111/nodejs:19`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | |
