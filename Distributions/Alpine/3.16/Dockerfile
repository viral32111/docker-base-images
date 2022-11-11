# syntax=docker/dockerfile:1

# Start from the official Alpine image
FROM alpine:3.16

# Configure the regular user & disable shell history
ENV USER_ID=1000 \
	USER_NAME=user \
	USER_HOME=/home/user \
	HISTFILE=/dev/null

# Download my container healthcheck utility
ARG HEALTHCHECK_VERSION=2.0.0
ADD --chmod=755 https://github.com/viral32111/healthcheck/releases/download/${HEALTHCHECK_VERSION}/healthcheck-linux-amd64-musl /usr/local/bin/healthcheck

# Add my personal CA root certificate
COPY --chmod=644 --chown=0:0 ./viral32111.crt /usr/local/share/ca-certificates/

# Install public CA certificates
RUN apk add --no-cache ca-certificates

# Switch to a package repository mirror hosted in the United Kingdom
RUN printf "%s\n%s\n" \
		"https://uk.alpinelinux.org/alpine/v3.16/main" \
		"https://uk.alpinelinux.org/alpine/v3.16/community" | tee /etc/apk/repositories

# Create the regular user
RUN mkdir -v -p ${USER_HOME} && \
	addgroup -S -g ${USER_ID} ${USER_NAME} && \
	adduser -S -D -s /sbin/nologin -H -h ${USER_HOME} -g ${USER_NAME} -G ${USER_NAME} -u ${USER_ID} ${USER_NAME} && \
	chown -c -R ${USER_ID}:${USER_ID} ${USER_HOME}

# Switch to the regular user's home directory
WORKDIR ${USER_HOME}
