FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN apk --update add dnsmasq supervisor

RUN echo http://dl-3.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories
RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk --update add libsodium dnscrypt-proxy nginx

RUN mkdir /etc/supervisor.d
RUN rm -fr /etc/dnsmasq.conf

RUN echo "interface=eth0" > /etc/dnsmasq.conf
RUN echo "listen-address=0.0.0.0" >> /etc/dnsmasq.conf
RUN echo "server=127.0.0.1#1053" >> /etc/dnsmasq.conf
RUN echo "server=/bit/192.184.93.146" >> /etc/dnsmasq.conf
RUN echo "server=/nxt/192.184.93.146" >> /etc/dnsmasq.conf
RUN echo "server=/p2p/192.184.93.146" >> /etc/dnsmasq.conf
RUN echo "proxy-dnssec" >> /etc/dnsmasq.conf
RUN echo "cache-size=4096" >> /etc/dnsmasq.conf
RUN mkdir /run/nginx

COPY supervisor.ini /etc/supervisor.d/supervisor.ini
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 53/tcp 53/udp

CMD /usr/bin/supervisord
