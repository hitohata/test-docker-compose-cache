FROM rust:1-bookworm

# sccach
ARG SCCACHE_VERSION=0.9.0
RUN ARCH=$(uname -m) \
    && curl -L -O https://github.com/mozilla/sccache/releases/download/v${SCCACHE_VERSION}/sccache-v${SCCACHE_VERSION}-${ARCH}-unknown-linux-musl.tar.gz \
    && tar xf sccache-* && \
    cp -p sccache-*/sccache /usr/local/bin/ && \
    rm -rf sccache-*

# mold
ARG MOLD_VERSION=2.35.1
RUN ARCH=$(uname -m) \
    && curl -L -O https://github.com/rui314/mold/releases/download/v${MOLD_VERSION}/mold-${MOLD_VERSION}-${ARCH}-linux.tar.gz \
    && tar xf mold-* && \
    cp -p mold-*/bin/* /usr/local/bin/ && \
    rm -rf mold-* \
