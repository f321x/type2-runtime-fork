FROM alpine:3.21@sha256:a8560b36e8b8210634f77d9f7f9efd7ffa463e380b75e2e74aff4511df3ef88c

# includes dependencies from https://git.alpinelinux.org/aports/tree/main/fuse3/APKBUILD
RUN apk add --no-cache \
    bash=5.2.37-r0 \ 
    alpine-sdk=1.1-r0 \ 
    util-linux=2.40.4-r1 \
    strace=6.12-r0 \
    file=5.46-r2 \
    autoconf=2.72-r0 \ 
    automake=1.17-r0 \
    libtool=2.4.7-r3 \
    xz=5.6.3-r1 \
    eudev-dev=3.2.14-r5 \ 
    gettext-dev=0.22.5-r0 \ 
    linux-headers=6.6-r1 \ 
    meson=1.6.1-r0 \
    zstd-dev=1.5.6-r2 \
    zstd-static=1.5.6-r2 \ 
    zlib-dev=1.3.1-r2 \
    zlib-static=1.3.1-r2 \ 
    clang19=19.1.4-r0 \
    musl-dev=1.2.5-r9 \ 
    mimalloc2-dev=2.1.7-r0

COPY scripts/common/install-dependencies.sh /tmp/scripts/common/install-dependencies.sh
COPY patches/ /tmp/patches/

# Set environment variables for reproducible build
ENV SOURCE_DATE_EPOCH=1640995200
ENV TZ=UTC
ENV LC_ALL=C

WORKDIR /tmp
RUN bash scripts/common/install-dependencies.sh