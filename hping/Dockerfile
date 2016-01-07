# hping - packet generator and analyzer for the TCP/IP protocol.

FROM debian:latest

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

RUN apt-get update && apt-get install -y \
    hping3 \
	&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["hping3"]