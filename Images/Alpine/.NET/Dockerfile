# https://dotnet.microsoft.com/en-us/download/dotnet/7.0
# https://learn.microsoft.com/en-gb/dotnet/core/install/linux-alpine#dependencies

# Start from Alpine
FROM ghcr.io/viral32111/alpine:3.17

# Configure version & directory
ARG DOTNET_VERSION=7.0.0 \
	DOTNET_DIRECTORY=/opt/dotnet

# Download & install .NET
RUN apk add --no-cache \
		wget \
		icu-libs krb5-libs libgcc libintl libssl1.1 libstdc++ zlib && \
	mkdir -v -p ${DOTNET_DIRECTORY} && \
	wget --progress dot:mega --output-document /tmp/dotnet.tar.gz https://dotnetcli.azureedge.net/dotnet/Runtime/${DOTNET_VERSION}/dotnet-runtime-${DOTNET_VERSION}-linux-musl-x64.tar.gz 2>&1 && \
	tar x -v -o --strip-components 1 \
		--exclude '*/LICENSE.txt' \
		--exclude '*/ThirdPartyNotices.txt' \
		-f /tmp/dotnet.tar.gz -C ${DOTNET_DIRECTORY} && \
	apk del --no-cache wget && \
	rm -v -r /tmp/dotnet.tar.gz

# Add .NET to the binaries path, set its install directory & disable telemetry
ENV PATH=${DOTNET_DIRECTORY}:$PATH \
	DOTNET_ROOT=${DOTNET_DIRECTORY} \
	DOTNET_CLI_TELEMETRY_OPTOUT=1

# Run commands with .NET
ENTRYPOINT [ "dotnet" ]
