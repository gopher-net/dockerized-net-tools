FROM debian

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

RUN apt-get update -qq \
    && apt-get install -y nmap \
    && apt-get clean

# A couple of example usages:
# [ docker run -it --rm networkstatic/nmap --help ]
# Scan for open ssh (tcp/22) ports on a range of IPs
# [ docker run -it --rm networkstatic/nmap -sT 192.168.1.1-100 -p 22 ]

ENTRYPOINT ["nmap"]