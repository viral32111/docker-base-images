# syntax=docker/dockerfile:1

# https://dotnet.microsoft.com/en-us/download/dotnet/6.0
# https://github.com/dotnet/core/blob/main/release-notes/6.0/linux-packages.md

# Start from Ubuntu
FROM ghcr.io/viral32111/ubuntu:22.10

# Configure version & directory
ARG ASPNETCORE_VERSION=7.0.0 \
	ASPNETCORE_DIRECTORY=/usr/local/aspnetcore

# Download & install .NET
RUN apt-get update && \
	apt-get install --no-install-recommends --yes \
		wget \
		libc6 libgcc1 libgssapi-krb5-2 libicu71 libssl3 libstdc++6 zlib1g && \
	mkdir --verbose --parents ${ASPNETCORE_DIRECTORY} && \
	wget --progress dot:mega --output-document /tmp/aspnetcore.tar.gz https://dotnetcli.azureedge.net/dotnet/aspnetcore/Runtime/${ASPNETCORE_VERSION}/aspnetcore-runtime-${ASPNETCORE_VERSION}-linux-x64.tar.gz 2>&1 && \
	tar --verbose --extract --strip-components 1 --file /tmp/aspnetcore.tar.gz --directory ${ASPNETCORE_DIRECTORY} && \
	apt-get remove --purge --autoremove --yes wget && \
	rm --verbose --recursive --force \
		/tmp/aspnetcore.tar.gz \
		${ASPNETCORE_DIRECTORY}/LICENSE.txt ${ASPNETCORE_DIRECTORY}/ThirdPartyNotices.txt \
		/var/log/* /var/lib/apt/lists/*

# Add .NET to the binaries path & disable telemetry
ENV PATH=${ASPNETCORE_DIRECTORY}:$PATH \
	DOTNET_ROOT=${ASPNETCORE_DIRECTORY} \
	DOTNET_CLI_TELEMETRY_OPTOUT=1

# Start .NET on launch
ENTRYPOINT [ "dotnet" ]
CMD [ "--help" ]
