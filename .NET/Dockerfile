# syntax=docker/dockerfile:1

# https://dotnet.microsoft.com/en-us/download/dotnet/6.0
# https://github.com/dotnet/core/blob/main/release-notes/6.0/linux-packages.md

# Start from Ubuntu
FROM ghcr.io/viral32111/ubuntu:22.10

# Configure version & directory
ARG DOTNET_VERSION=7.0.0 \
	DOTNET_DIRECTORY=/usr/local/dotnet

# Download & install .NET
RUN apt-get update && \
	apt-get install --no-install-recommends --yes \
		wget \
		libc6 libgcc1 libgssapi-krb5-2 libicu71 libssl3 libstdc++6 zlib1g && \
	mkdir --verbose --parents ${DOTNET_DIRECTORY} && \
	wget --progress dot:mega --output-document /tmp/dotnet.tar.gz https://dotnetcli.azureedge.net/dotnet/Runtime/${DOTNET_VERSION}/dotnet-runtime-${DOTNET_VERSION}-linux-x64.tar.gz 2>&1 && \
	tar --verbose --extract --strip-components 1 --file /tmp/dotnet.tar.gz --directory ${DOTNET_DIRECTORY} && \
	apt-get remove --purge --autoremove --yes wget && \
	rm --verbose --recursive --force \
		/tmp/dotnet.tar.gz \
		${DOTNET_DIRECTORY}/LICENSE.txt ${DOTNET_DIRECTORY}/ThirdPartyNotices.txt \
		/var/log/* /var/lib/apt/lists/*

# Add .NET to the binaries path & disable telemetry
ENV PATH=${DOTNET_DIRECTORY}:$PATH \
	DOTNET_ROOT=${DOTNET_DIRECTORY} \
	DOTNET_CLI_TELEMETRY_OPTOUT=1

# Start .NET on launch
ENTRYPOINT [ "dotnet" ]
CMD [ "--help" ]
