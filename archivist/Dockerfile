FROM alpine:latest
MAINTAINER Laam Alif <BM-2cTcqbjfH3kg9FrhMPoxJ2DrTzE5UAeQT5@bitmessage.ch>

RUN apk --update add py-pillow py-requests py2-pip graphicsmagick
RUN pip install beautifulsoup4
RUN rm -rf /var/cache/apk/*
RUN mkdir /rekhta
COPY rekhta /usr/bin/
WORKDIR /rekhta
ENTRYPOINT [ "rekhta" ]
