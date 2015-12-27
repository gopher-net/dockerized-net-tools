FROM debian

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

# build initial cache | install binary | remove cache
RUN apt-get update -qq \
    && apt-get install -y fping \
    && apt-get clean

# The usage example will execute fping and any arguments passed.
# once complete, Docker will delete the container if --rm was used:
# Try it out with: docker run -it --rm networkstatic/fping -help

ENTRYPOINT ["fping"]