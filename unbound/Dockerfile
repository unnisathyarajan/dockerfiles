FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN apk --update add supervisor unbound

RUN echo http://dl-3.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories
RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN echo http://nl.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories
RUN apk --update add libsodium dnscrypt-proxy

RUN mkdir /etc/supervisor.d

COPY supervisor.ini /etc/supervisor.d/supervisor.ini
COPY unbound.conf /etc/unbound/unbound.conf

EXPOSE 53/tcp 53/udp

CMD /usr/bin/supervisord
