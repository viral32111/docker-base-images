# syntax=docker/dockerfile:1

# https://alpinelinux.org/downloads/

# Start from nothing
FROM scratch

# Configure versions
ARG ALPINE_BRANCH=3.17 \
	HEALTHCHECK_VERSION=2.0.0

# Extract the root filesystem
ADD --chown=0:0 ./alpine.tar.gz /

# Add my personal CA root certificate
COPY --chmod=644 --chown=0:0 ./viral32111.crt /usr/local/share/ca-certificates/

# Upgrade packages & install public CA certificates
RUN apk upgrade --no-cache && \
	apk add --no-cache ca-certificates

# Switch to a package repository mirror hosted in the United Kingdom
RUN printf "%s\n%s\n" \
		"https://uk.alpinelinux.org/alpine/v${ALPINE_BRANCH}/main" \
		"https://uk.alpinelinux.org/alpine/v${ALPINE_BRANCH}/community" | tee /etc/apk/repositories

# Download my container healthcheck utility
ADD --chmod=755 https://github.com/viral32111/healthcheck/releases/download/${HEALTHCHECK_VERSION}/healthcheck-linux-amd64-musl /usr/local/bin/healthcheck

# Configure the regular user & disable shell history
ENV USER_ID=1000 \
	USER_NAME=user \
	USER_HOME=/home/user \
	HISTFILE=/dev/null

# Create the regular user
RUN mkdir -v -p ${USER_HOME} && \
	addgroup -S -g ${USER_ID} ${USER_NAME} && \
	adduser -S -D -s /sbin/nologin -H -h ${USER_HOME} -g ${USER_NAME} -G ${USER_NAME} -u ${USER_ID} ${USER_NAME} && \
	chown -c -R ${USER_ID}:${USER_ID} ${USER_HOME}

# Switch to the regular user's home directory
WORKDIR ${USER_HOME}

# Start a shell by default
CMD [ "sh" ]
