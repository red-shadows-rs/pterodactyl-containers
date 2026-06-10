FROM --platform=$TARGETOS/$TARGETARCH debian:bookworm-slim

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

LABEL author="RED SHADOWS | RS" \
    maintainer="support@red-shadows-rs.com" \
    version="12.0.0" \
    description="code-server runtime for Pterodactyl Panel" \
    org.opencontainers.image.source="https://github.com/red-shadows-rs/pterodactyl-containers" \
    org.opencontainers.image.vendor="RED SHADOWS | RS" \
    org.opencontainers.image.title="Pterodactyl code-server" \
    org.opencontainers.image.description="Secure code-server container for Pterodactyl with VS Code in the browser"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    lsof \
    ca-certificates \
    openssl \
    git \
    git-lfs \
    tar \
    sqlite3 \
    fontconfig \
    iproute2 \
    libfreetype6 \
    zip \
    unzip \
    procps \
    nano \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && ARCH=$(dpkg --print-architecture) \
    && CODESERVER_VERSION=$(curl -fsSL "https://api.github.com/repos/coder/code-server/releases/latest" | grep '"tag_name"' | sed -E 's/.*"v([^"]+)".*/\1/') \
    && curl -fsSL "https://github.com/coder/code-server/releases/download/v${CODESERVER_VERSION}/code-server_${CODESERVER_VERSION}_${ARCH}.deb" -o /tmp/code-server.deb \
    && dpkg -i /tmp/code-server.deb \
    && rm -f /tmp/code-server.deb \
    && useradd -m -d /home/container -s /bin/bash container \
    && chown container:container /home/container

USER container
ENV USER=container \
    HOME=/home/container

WORKDIR /home/container

HEALTHCHECK --interval=30s --timeout=10s --start-period=10s --retries=3 \
    CMD code-server --version 2>&1 | head -1 || exit 1

STOPSIGNAL SIGTERM

COPY ./entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]
