# syntax=docker/dockerfile:1

# https://github.com/adoptium/temurin19-binaries/releases/latest
# This image works for Java 11, 17, 18 & 19, as they all use the modern versioning scheme.

# Start from Ubuntu
FROM ghcr.io/viral32111/ubuntu:22.10

# Configure version & directory
ARG JAVA_VERSION_MAJOR=19 \
	JAVA_VERSION_LATEST=19.0.1+10 \
	JAVA_DIRECTORY=/usr/local/java

# Download Java from Adoptium Temurin
RUN apt-get update && \
	apt-get install --no-install-recommends --yes wget && \
	mkdir --verbose --parents ${JAVA_DIRECTORY} && \
	export JAVA_VERSION_FILE=$(echo "${JAVA_VERSION_LATEST}" | sed 's/\+/_/') && \
	wget --no-hsts --progress dot:mega --output-document /tmp/java.tar.gz https://github.com/adoptium/temurin${JAVA_VERSION_MAJOR}-binaries/releases/download/jdk-${JAVA_VERSION_LATEST}/OpenJDK${JAVA_VERSION_MAJOR}U-jre_x64_linux_hotspot_${JAVA_VERSION_FILE}.tar.gz 2>&1 && \
	tar --verbose --extract --no-same-owner --strip-components 1 --file /tmp/java.tar.gz --directory ${JAVA_DIRECTORY} && \
	apt-get remove --purge --autoremove --yes wget && \
	apt-get clean --yes && \
	rm --verbose --force --recursive \
		/tmp/java.tar.gz \
		${JAVA_DIRECTORY}/NOTICE \
		/var/lib/apt/lists/*

# Add Java to the binaries path
ENV PATH=${JAVA_DIRECTORY}/bin:$PATH

# Show Java version on launch
ENTRYPOINT [ "java" ]
CMD [ "--version" ]
