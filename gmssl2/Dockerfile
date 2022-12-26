FROM alpine:3.17

RUN apk add --no-cache build-base linux-headers curl perl

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
