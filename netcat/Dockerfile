# netcat in a container
# Start a listener:
# $ docker run -it --rm  -p 9000:9000 networkstatic/netcat -l 9000
#
# Get the IP of the docker:
# $ docker inspect --format "{{ .NetworkSettings.IPAddress }}" $(docker ps -q)
#
# Connect to the listener w/ a new container:
# $ docker run -it --rm  networkstatic/netcat 172.17.0.1 9000

FROM debian

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

# Install the app
RUN apt-get update && apt-get install -y \
	netcat-openbsd \
	&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT [ "nc" ]