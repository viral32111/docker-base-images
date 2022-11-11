# syntax=docker/dockerfile:1

# Start from the official Ubuntu image
FROM ubuntu:22.10

# Configure the regular user & disable shell history
ENV USER_ID=1000 \
	USER_NAME=user \
	USER_HOME=/home/user \
	HISTFILE=/dev/null

# Download my container healthcheck utility
ARG HEALTHCHECK_VERSION=2.0.0
ADD --chmod=755 https://github.com/viral32111/healthcheck/releases/download/${HEALTHCHECK_VERSION}/healthcheck-linux-amd64-glibc /usr/local/bin/healthcheck

# Add my personal CA root certificate
COPY --chmod=644 --chown=0:0 ./viral32111.crt /usr/local/share/ca-certificates/viral32111.crt

# Install public CA certificates
RUN apt-get update && \
	apt-get install --no-install-recommends --yes ca-certificates && \
	rm --verbose --force --recursive /var/log/* /var/lib/apt/lists/*

# Switch to secure package repository mirror hosted in the United Kingdom
RUN printf "%s\n%s\n%s\n%s\n" \
		"deb https://www.mirrorservice.org/sites/archive.ubuntu.com/ubuntu/ kinetic main restricted universe multiverse" \
		"deb https://www.mirrorservice.org/sites/archive.ubuntu.com/ubuntu/ kinetic-updates main restricted universe multiverse" \
		"deb https://www.mirrorservice.org/sites/archive.ubuntu.com/ubuntu/ kinetic-backports main restricted universe multiverse" \
		"deb http://security.ubuntu.com/ubuntu/ kinetic-security main restricted universe multiverse" | tee /etc/apt/sources.list

# Create the regular user
RUN mkdir --verbose --parents ${USER_HOME} && \
	adduser --system --disabled-password --disabled-login --shell /usr/sbin/nologin --no-create-home --home ${USER_HOME} --gecos ${USER_NAME} --group --uid ${USER_ID} ${USER_NAME} && \
	chown --changes --recursive ${USER_ID}:${USER_ID} ${USER_HOME}

# Switch to the regular user's home directory
WORKDIR	${USER_HOME}
