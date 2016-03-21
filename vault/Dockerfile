FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk --update add vault
RUN rm -rf /var/cache/apk/*
COPY vault.hcl /etc/vault.hcl
EXPOSE 8200/tcp
CMD vault server -config /etc/vault.hcl
