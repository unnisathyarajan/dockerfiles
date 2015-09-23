FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

ENV LISTEN_ADDR 0.0.0.0:1053
ENV RESOLVER_ADDR 23.226.227.93:443
ENV PROVIDER_NAME 2.dnscrypt-cert.okturtles.com
ENV PROVIDER_KEY 1D85:3953:E34F:AFD0:05F9:4C6F:D1CC:E635:D411:9904:0D48:D19A:5D35:0B6A:7C81:73CB
RUN echo http://dl-3.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories
RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk --update add libsodium dnscrypt-proxy


EXPOSE 1053/tcp 1053/udp

CMD dnscrypt-proxy --local-address=$LISTEN_ADDR \
                   --provider-name=$PROVIDER_NAME \
                   --provider-key=$PROVIDER_KEY \
                   --resolver-address=$RESOLVER_ADDR
