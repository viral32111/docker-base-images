# Docker Base Images

This repository builds & publishes my base Docker images that I use across all my other projects.

**I do not recommend that you use these images in your own projects as they are tailored towards my needs!**

## Distributions

These are the Linux distribution images I use the base for all my other images.

These images are built from root filesystem tarballs, and will always use the latest stable version for each major release.

The following changes have been made within these images:
 * Switched to a package repository mirror in the United Kingdom.
 * Switched to British English locale & UTF-8 character set.
 * Switched to UTC timezone.
 * Installed public CA certificates & my [personal root CA certificate](context/viral32111.crt).
 * Installed my [container healthcheck](https://github.com/viral32111/healthcheck) utility.
 * Created a standard, unprivileged user & group (UID & GID: `1000`).
 * Added local user binaries to the system path.
 * Disabled writing shell history to file.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Ubuntu 18.04](https://www.releases.ubuntu.com/bionic/) | 18.04.5 | [`ghcr.io/viral32111/ubuntu:18.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 20.04](https://www.releases.ubuntu.com/focal/) | 20.04.5 | [`ghcr.io/viral32111/ubuntu:20.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 22.04](https://www.releases.ubuntu.com/jammy/) | 22.04.2 | [`ghcr.io/viral32111/ubuntu:22.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 22.10](https://www.releases.ubuntu.com/kinetic/) | 22.10 | [`ghcr.io/viral32111/ubuntu:22.10`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| [Ubuntu 23.04](https://www.releases.ubuntu.com/lunar/) | 23.04 | [`ghcr.io/viral32111/ubuntu:23.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| ~~[Alpine Linux 3.15](https://alpinelinux.org/)~~ | ~~3.15.6~~ | ~~[`ghcr.io/viral32111/alpine:3.15`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine)~~ | Deprecated. |
| [Alpine Linux 3.16](https://alpinelinux.org/) | 3.16.5 | [`ghcr.io/viral32111/alpine:3.16`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.17](https://alpinelinux.org/) | 3.17.3 | [`ghcr.io/viral32111/alpine:3.17`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |

## Java

These images use Java from [Adoptium Temurin](https://adoptium.net/temurin/releases/), and will always use the latest stable version for each major release.

These images are based on both Ubuntu 22.10 and Alpine Linux 3.17.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Java 8](https://adoptium.net) | 8u362-b09 | [`ghcr.io/viral32111/java:8`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 11](https://adoptium.net) | 11.0.18+10 | [`ghcr.io/viral32111/java:11`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 16](https://adoptium.net) | 16.0.2+7 | [`ghcr.io/viral32111/java:16`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | Uses JDK instead of JRE. |
| [Java 17](https://adoptium.net) | 17.0.6+10 | [`ghcr.io/viral32111/java:17`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 18](https://adoptium.net) | 18.0.2.1+1 | [`ghcr.io/viral32111/java:18`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 19](https://adoptium.net) | 19.0.2+7 | [`ghcr.io/viral32111/java:19`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |

## .NET

These images are based on both Ubuntu 22.10 and Alpine Linux 3.17.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [.NET Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.15 | [`ghcr.io/viral32111/dotnet:6.0`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |
| [.NET Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.4 | [`ghcr.io/viral32111/dotnet:7.0`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [ASP.NET Core Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.15 | [`ghcr.io/viral32111/aspnetcore:6.0`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |
| [ASP.NET Core Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.4 | [`ghcr.io/viral32111/aspnetcore:7.0`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |

## Node.js

These images are based on Ubuntu 22.10.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Node.js v18](https://nodejs.org) | 18.15.0 | [`ghcr.io/viral32111/nodejs:18`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | |
| [Node.js v19](https://nodejs.org) | 19.8.1 | [`ghcr.io/viral32111/nodejs:19`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | |


## Python

These images are based on Ubuntu 22.10.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Python 3](https://python.org) | 3.11.2 | [`ghcr.io/viral32111/python:3`](https://github.com/viral32111/docker-base-images/pkgs/container/python) | |
