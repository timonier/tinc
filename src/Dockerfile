FROM alpine:3.4

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    TINC_VERSION=1.0.28

RUN set -x \

    # Install packages

    && apk add --no-cache --no-progress --virtual build_deps \
           build-base \
           ca-certificates \
           curl \
           libpcap-dev \
           linux-headers \
           lzo-dev \
           openssl-dev \
           zlib-dev \

    && apk add --no-cache --no-progress \
           libpcap \
           libcrypto1.0 \
           lzo \
           zlib \

    # Install tinc

    && curl -sL "https://www.tinc-vpn.org/packages/tinc-${TINC_VERSION}.tar.gz" | tar fxz - -C /tmp \
    && sh -c "cd /tmp/tinc-${TINC_VERSION} && ./configure --enable-jumbograms --enable-lzo --enable-tunemu --enable-zlib --localstatedir=/var --prefix=/usr --sysconfdir=/etc" \
    && make -C /tmp/tinc-${TINC_VERSION} \
    && make -C /tmp/tinc-${TINC_VERSION} install \

    # Install timonier/dumb-entrypoint

    && curl -sL "https://github.com/timonier/dumb-entrypoint/raw/master/bin/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s install \

    # Clean

    && apk del --no-progress \
           build_deps \

    && rm -rf \
           /tmp/*

ENTRYPOINT [ "/usr/sbin/dumb-init" , "--" , "/usr/sbin/dumb-entrypoint" ]
