# mz (Mausezahn) in a container

FROM debian

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

# Install the app
RUN apt-get update && apt-get install -y \
	mz \
	&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT [ "mz" ]