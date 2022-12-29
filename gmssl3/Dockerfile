FROM alpine:3.17

RUN apk add --no-cache build-base curl cmake

WORKDIR /tmp/gmssl
RUN set -xe; \
    curl -sL https://github.com/guanzhi/GmSSL/archive/refs/tags/v3.0.0.tar.gz \
    | tar -xzC /tmp/gmssl --strip-components 1

RUN set -xe; \
    mkdir build \
    && cd build \
    && cmake .. \
    && make -j$(nproc) \
    && make install

WORKDIR /data
ENTRYPOINT ["gmssl"]
