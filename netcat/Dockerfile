# netcat in a container
# Start a listener:
# $ docker run -it --rm  -p 9000:9000 gophernet/netcat -l 9000
#
# Get the IP of the docker:
# $ docker inspect --format "{{ .NetworkSettings.IPAddress }}" $(docker ps -q)
#
# Connect to the listener w/ a new container:
# $ docker run -it --rm  gophernet/netcat 172.17.0.1 9000
#
FROM alpine:latest

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

ENTRYPOINT [ "nc" ]
