FROM --platform=$TARGETOS/$TARGETARCH node:22-bookworm-slim

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

LABEL author="RED SHADOWS | RS" \
    maintainer="support@red-shadows-rs.com" \
    version="13.1.0" \
    description="n8n runtime for Pterodactyl Panel" \
    org.opencontainers.image.source="https://github.com/red-shadows-rs/pterodactyl-containers" \
    org.opencontainers.image.vendor="RED SHADOWS | RS" \
    org.opencontainers.image.title="Pterodactyl n8n" \
    org.opencontainers.image.description="Secure n8n container for Pterodactyl with workflow automation"

ENV DEBIAN_FRONTEND=noninteractive
ENV N8N_PORT=5678
ENV N8N_PROTOCOL=http
ENV N8N_HOST=localhost

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    ca-certificates \
    openssl \
    git \
    tar \
    sqlite3 \
    procps \
    nano \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && npm install -g n8n \
    && useradd -m -d /home/container -s /bin/bash container \
    && chown container:container /home/container

USER container
ENV USER=container \
    HOME=/home/container

WORKDIR /home/container

HEALTHCHECK --interval=30s --timeout=10s --start-period=15s --retries=3 \
    CMD n8n --version 2>&1 | head -1 || exit 1

STOPSIGNAL SIGTERM

COPY ./entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]
