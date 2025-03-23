ARG BUILD_FROM
FROM ${BUILD_FROM}

# Add-on metadata
LABEL \
    io.hass.name="Porcupine Wake Word (v3)" \
    io.hass.description="Wake word detection using the Wyoming protocol with Porcupine v3" \
    io.hass.version="3.0.0" \
    io.hass.type="addon" \
    io.hass.arch="amd64,aarch64,armv7"

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Install packages
RUN \
    apk add --no-cache \
        git \
        py3-pip \
        py3-virtualenv \
        python3

WORKDIR /usr/src

# Create virtual environment
RUN python3 -m venv .venv

# Clone repository
RUN \
    git clone https://github.com/vash2695/wyoming-porcupine.git && \
    cd wyoming-porcupine && \
    ../.venv/bin/pip3 install --no-cache-dir -e .

# Copy data for add-on
COPY rootfs /

# Wyoming server configuration
ENV PYTHONPATH=/usr/src
EXPOSE 10400

ENTRYPOINT ["/init"] 