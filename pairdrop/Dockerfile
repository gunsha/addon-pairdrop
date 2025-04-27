ARG BUILD_FROM=ghcr.io/hassio-addons/base:17.2.3
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Required for webpack config of NPM
ENV NODE_OPTIONS="--openssl-legacy-provider"

# Setup base
ARG PAIRDROP_VERSION="v1.11.2"

# hadolint ignore=DL3003,DL3042
RUN \
    apk update \
    && apk add --no-cache --virtual .build-dependencies \
        npm \
    \
    && apk add --no-cache \
        nodejs \
    \
    && curl -J -L -o /tmp/pairdrop.tar.gz \
        "https://github.com/schlagmichdoch/PairDrop/archive/refs/tags/v1.11.2.tar.gz" \
    && mkdir -p /opt/pairdrop \
    && tar zxvf \
        /tmp/pairdrop.tar.gz \
        --strip 1 -C /opt/pairdrop \
    \
    && cd /opt/pairdrop \
    && npm ci

# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Gonzalo Aller <gonzaller@gmail.com>" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="Home Assistant Community Add-ons" \
    org.opencontainers.image.authors="Gonzalo Aller <gonzaller@gmail.com>" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://addons.community" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}