# https://dotnet.microsoft.com/en-us/download/dotnet/7.0
# https://learn.microsoft.com/en-gb/dotnet/core/install/linux-alpine#dependencies

# Start from Alpine
FROM ghcr.io/viral32111/alpine:3.17

# Configure version & directory
ARG ASPNETCORE_VERSION=7.0.0 \
	ASPNETCORE_DIRECTORY=/opt/aspnetcore

# Download & install .NET
RUN apk add --no-cache \
		wget \
		icu-libs krb5-libs libgcc libintl libssl1.1 libstdc++ zlib && \
	mkdir -v -p ${ASPNETCORE_DIRECTORY} && \
	wget --progress dot:mega --output-document /tmp/aspnetcore.tar.gz https://dotnetcli.azureedge.net/dotnet/aspnetcore/Runtime/${ASPNETCORE_VERSION}/aspnetcore-runtime-${ASPNETCORE_VERSION}-linux-musl-x64.tar.gz 2>&1 && \
	tar x -v -o --strip-components 1 \
		--exclude '*/LICENSE.txt' \
		--exclude '*/ThirdPartyNotices.txt' \
		-f /tmp/aspnetcore.tar.gz -C ${ASPNETCORE_DIRECTORY} && \
	apk del --no-cache wget && \
	rm -v -r /tmp/aspnetcore.tar.gz

# Add .NET to the binaries path, set its install directory & disable telemetry
ENV PATH=${ASPNETCORE_DIRECTORY}:$PATH \
	DOTNET_ROOT=${ASPNETCORE_DIRECTORY} \
	DOTNET_CLI_TELEMETRY_OPTOUT=1

# Run commands with .NET
ENTRYPOINT [ "dotnet" ]
