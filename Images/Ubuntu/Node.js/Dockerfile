# https://nodejs.org/en/download/current/
# https://unofficial-builds.nodejs.org/download/release/v19.2.0/

# Start from Ubuntu
# NOTE: We use Ubuntu instead of Alpine as the musl build of Node.js is slightly bigger than the glibc build! (it's also unofficial)
FROM ghcr.io/viral32111/ubuntu:22.10

# Configure the version & directory
ARG NODEJS_VERSION=19.2.0 \
	NODEJS_DIRECTORY=/opt/nodejs

# Download & extract the Node.js pre-built binaries
RUN apt-get update && \
	apt-get install --no-install-recommends --yes wget && \
	mkdir --verbose --parents ${NODEJS_DIRECTORY} && \
	wget --no-hsts --progress dot:mega --output-document /tmp/nodejs.tar.gz https://nodejs.org/dist/v${NODEJS_VERSION}/node-v${NODEJS_VERSION}-linux-x64.tar.gz 2>&1 && \
	tar --verbose --extract --no-same-owner --strip-components 1 --file /tmp/nodejs.tar.gz --directory ${NODEJS_DIRECTORY} \
		--exclude '*/README.md' \
		--exclude '*/CHANGELOG.md' \
		--exclude '*/LICENSE' \
		--exclude '*/share/man' && \
	apt-get remove --purge --auto-remove --yes wget && \
	apt-get clean --yes && \
	rm --verbose --recursive \
		/tmp/nodejs.tar.gz \
		/var/lib/apt/lists/*

# Add Node.js to the binaries & libraries paths, and set the Node.js environment to production
ENV PATH=${NODEJS_DIRECTORY}/bin:$PATH \
	LD_LIBRARY_PATH=${NODEJS_DIRECTORY}/lib:$LD_LIBRARY_PATH \
	NODE_ENV=production

# Update NPM to the latest version
RUN npm install --global npm@latest && \
	npm cache clean --force && \
	rm --verbose --recursive $HOME/.npm

# Run commands with Node.js
ENTRYPOINT [ "node" ]
