# © Copyright RED SHADOWS | RS - Shadow-x78

FROM --platform=$TARGETOS/$TARGETARCH eclipse-temurin:17-jdk-jammy

LABEL author="Shadow-x78" \
      maintainer="support@red-shadows-rs.com" \
      version="1.0.0" \
      description="Java 17 LTS runtime for Pterodactyl Panel" \
      org.opencontainers.image.source="https://github.com/RED-SHADOWS-RS/PterodactylContainer" \
      org.opencontainers.image.vendor="RED SHADOWS | RS" \
      org.opencontainers.image.title="Pterodactyl Java 17" \
      org.opencontainers.image.description="Secure Java 17 LTS container for Pterodactyl"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        curl \
        lsof \
        ca-certificates \
        openssl \
        git \
        tar \
        sqlite3 \
        fontconfig \
        tzdata \
        iproute2 \
        libfreetype6 \
        zip \
        unzip \
        procps \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && useradd -m -d /home/container -s /bin/bash container \
    && chown container:container /home/container

USER container
ENV USER=container \
    HOME=/home/container \
    JAVA_OPTS="-XX:+UseG1GC -XX:+UseStringDeduplication" \
    TZ=UTC

WORKDIR /home/container

HEALTHCHECK --interval=30s --timeout=10s --start-period=10s --retries=3 \
    CMD java -version 2>&1 | grep -q "Eclipse Temurin" || exit 1

STOPSIGNAL SIGTERM

COPY ./entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]
