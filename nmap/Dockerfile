# nmap in a container
# A couple of example usages:
# [ docker run -it --rm networkstatic/nmap --help ]
# Scan for open ssh (tcp/22) ports on a range of IPs
# [ docker run -it --rm networkstatic/nmap -sT 192.168.1.1-100 -p 22 ]
#
FROM alpine:latest

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

# build initial cache | install binary | remove cache
RUN apk update && apk add \
	nmap \
	&& rm -rf /var/cache/apk/*

ENTRYPOINT ["nmap"]
