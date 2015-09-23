FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

ENV LISTEN_ADDR 0.0.0.0:2053
ENV RESOLVER_ADDR 77.66.84.233:443
ENV PROVIDER_NAME 2.dnscrypt-cert.resolver2.dnscrypt.eu
ENV PROVIDER_KEY 3748:5585:E3B9:D088:FD25:AD36:B037:01F5:520C:D648:9E9A:DD52:1457:4955:9F0A:9955
RUN echo http://dl-3.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories
RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk --update add libsodium dnscrypt-proxy


EXPOSE 2053/tcp 2053/udp

CMD dnscrypt-proxy --local-address=$LISTEN_ADDR \
                   --provider-name=$PROVIDER_NAME \
                   --provider-key=$PROVIDER_KEY \
                   --resolver-address=$RESOLVER_ADDR
