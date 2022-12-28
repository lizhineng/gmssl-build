FROM ubuntu:20.04

RUN apt-get update \
    && apt-get install -y build-essential curl \
    && rm -rf /var/lib/apt/lists/*

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib

WORKDIR /tmp/gmssl
RUN set -xe; \
    curl -sL https://github.com/guanzhi/GmSSL/archive/refs/heads/GmSSL-v2.tar.gz \
    | tar -xzC /tmp/gmssl --strip-components 1

RUN set -xe; \
    ./config \
    && make \
    && make install

WORKDIR /data
ENTRYPOINT ["gmssl"]
