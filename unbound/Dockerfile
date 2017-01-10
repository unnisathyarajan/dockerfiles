FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN apk --update add supervisor unbound libsodium dnscrypt-proxy

RUN mkdir /etc/supervisor.d

COPY supervisor.ini /etc/supervisor.d/supervisor.ini
COPY unbound.conf /etc/unbound/unbound.conf
COPY adaway.conf /etc/unbound/adaway.conf

EXPOSE 53/tcp 53/udp

CMD /usr/bin/supervisord
