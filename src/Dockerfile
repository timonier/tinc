FROM debian:jessie
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    TINC_VERSION=1.0.28

RUN set -x \

    # Prepare system

    && export DEBIAN_FRONTEND=noninteractive \

    && apt-get update \

    # Install packages

    && BUILD_DEPS="build-essential ca-certificates curl liblzo2-dev libssl-dev libz-dev" \

    && apt-get install -y --no-install-recommends \
           $BUILD_DEPS \
           liblzo2-2 \
           libssl1.0.0 \
           net-tools \

    # Install tinc

    && curl -sL "https://www.tinc-vpn.org/packages/tinc-$TINC_VERSION.tar.gz" | tar fxz - -C /tmp \
    && sh -c "cd /tmp/tinc-$TINC_VERSION && ./configure --enable-jumbograms --enable-lzo --enable-zlib --localstatedir=/var --prefix=/usr --sysconfdir=/etc" \
    && make -C /tmp/tinc-$TINC_VERSION \
    && make -C /tmp/tinc-$TINC_VERSION install \

    # Clean

    && apt-get remove -y --purge $BUILD_DEPS \
    && apt-get autoremove -y --purge \

    && rm -rf \
           /tmp/* \
           /var/lib/apt/lists/*

ENTRYPOINT [ "/usr/sbin/tincd" ]
