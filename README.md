# Docker Base Images

This repository builds & publishes my base Docker images that I use across all my other projects.

**I do not recommend that you use these images in your own projects as they are tailored towards my needs!**

## Distributions

These are the Linux distribution images I use the base for all my other images.

These images are built from root filesystem tarballs, and will always use the latest stable version for each major release. There are variants for 64-bit x86 & 64-bit ARM.

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
| [Ubuntu 18.04](https://www.releases.ubuntu.com/bionic/) | 18.04.6 | [`ghcr.io/viral32111/ubuntu:18.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | LTS. |
| [Ubuntu 20.04](https://www.releases.ubuntu.com/focal/) | 20.04.6 | [`ghcr.io/viral32111/ubuntu:20.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | LTS. |
| [Ubuntu 22.04](https://www.releases.ubuntu.com/jammy/) | 22.04.3 | [`ghcr.io/viral32111/ubuntu:22.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | LTS. |
| ~~[Ubuntu 22.10](https://www.releases.ubuntu.com/kinetic/)~~ | ~~22.10~~ | ~~[`ghcr.io/viral32111/ubuntu:22.10`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu)~~ | EOL. |
| [Ubuntu 23.04](https://www.releases.ubuntu.com/lunar/) | 23.04 | [`ghcr.io/viral32111/ubuntu:23.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |
| ~~[Ubuntu 23.10](https://releases.ubuntu.com/mantic/)~~ | ~~23.10~~ | ~~[`ghcr.io/viral32111/ubuntu:23.10`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu)~~ | EOL. |
| [Ubuntu 24.04](https://releases.ubuntu.com/noble/) | 24.04 | [`ghcr.io/viral32111/ubuntu:24.04`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | LTS. |
| [Ubuntu 24.10](https://releases.ubuntu.com/releases/24.10/) | 24.10 | [`ghcr.io/viral32111/ubuntu:24.10`](https://github.com/viral32111/docker-base-images/pkgs/container/ubuntu) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| ~~[Alpine Linux 3.15](https://alpinelinux.org/)~~ | ~~3.15.6~~ | ~~[`ghcr.io/viral32111/alpine:3.15`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine)~~ | EOL. |
| [Alpine Linux 3.16](https://alpinelinux.org/) | 3.16.7 | [`ghcr.io/viral32111/alpine:3.16`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.17](https://alpinelinux.org/) | 3.17.5 | [`ghcr.io/viral32111/alpine:3.17`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.18](https://alpinelinux.org/) | 3.18.3 | [`ghcr.io/viral32111/alpine:3.18`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.19](https://alpinelinux.org/) | 3.19.1 | [`ghcr.io/viral32111/alpine:3.19`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |
| [Alpine Linux 3.20](https://alpinelinux.org/) | 3.20.3 | [`ghcr.io/viral32111/alpine:3.20`](https://github.com/viral32111/docker-base-images/pkgs/container/alpine) | |

## Java

These images use Java from [Adoptium Temurin](https://adoptium.net/temurin/releases/), and will always use the latest stable version for each major release.

These images are based on both Ubuntu 24.10 and Alpine Linux 3.20, for 64-bit x86.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Java 8](https://adoptium.net) | 8u382-b05 | [`ghcr.io/viral32111/java:8`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 11](https://adoptium.net) | 11.0.20.1+1 | [`ghcr.io/viral32111/java:11`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 16](https://adoptium.net) | 16.0.2+7 | [`ghcr.io/viral32111/java:16`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | Uses JDK instead of JRE. |
| [Java 17](https://adoptium.net) | 17.0.8.1+1 | [`ghcr.io/viral32111/java:17`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | LTS. |
| [Java 18](https://adoptium.net) | 18.0.2.1+1 | [`ghcr.io/viral32111/java:18`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 19](https://adoptium.net) | 19.0.2+7 | [`ghcr.io/viral32111/java:19`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 20](https://adoptium.net) | 20.0.2+9 | [`ghcr.io/viral32111/java:20`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |
| [Java 21](https://adoptium.net) | 21.x | [`ghcr.io/viral32111/java:21`](https://github.com/viral32111/docker-base-images/pkgs/container/java) | |

## .NET

These images are based on both Ubuntu 24.10 and Alpine Linux 3.20, for 64-bit x86.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [.NET Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.22 | [`ghcr.io/viral32111/dotnet:6`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | LTS. |
| [.NET Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.11 | [`ghcr.io/viral32111/dotnet:7`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |
| [.NET Runtime 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) | 8.x | [`ghcr.io/viral32111/dotnet:8`](https://github.com/viral32111/docker-base-images/pkgs/container/dotnet) | |

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [ASP.NET Core Runtime 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) | 6.0.22 | [`ghcr.io/viral32111/aspnetcore:6`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | LTS. |
| [ASP.NET Core Runtime 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 7.0.11 | [`ghcr.io/viral32111/aspnetcore:7`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |
| [ASP.NET Core Runtime 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) | 8.x | [`ghcr.io/viral32111/aspnetcore:8`](https://github.com/viral32111/docker-base-images/pkgs/container/aspnetcore) | |

## Node.js

These images are based on both Ubuntu 24.10 and Alpine Linux 3.20, for 64-bit x86.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Node.js v18](https://nodejs.org) | 18.17.1 | [`ghcr.io/viral32111/nodejs:18`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | LTS. |
| ~~[Node.js v19](https://nodejs.org)~~ | ~~19.9.0~~ | ~~[`ghcr.io/viral32111/nodejs:19`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs)~~ | EOL. |
| [Node.js v20](https://nodejs.org) | 20.6.1 | [`ghcr.io/viral32111/nodejs:20`](https://github.com/viral32111/docker-base-images/pkgs/container/nodejs) | |

## Python

These images are based on Ubuntu 24.10.

| Title | Version | Image name & tag | Note |
| ----- | ------- | ---------------- | ---- |
| [Python 3](https://python.org) | 3.11.5 | [`ghcr.io/viral32111/python:3`](https://github.com/viral32111/docker-base-images/pkgs/container/python) | |
