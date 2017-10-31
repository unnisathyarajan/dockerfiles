FROM alpine:edge
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk --update add py-pillow py-requests py2-pip exiftool py-img2pdf py-beautifulsoup4 py-lxml
RUN rm -rf /var/cache/apk/*
RUN mkdir /rekhta
COPY rekhta /usr/bin/
WORKDIR /rekhta
ENTRYPOINT [ "rekhta" ]

