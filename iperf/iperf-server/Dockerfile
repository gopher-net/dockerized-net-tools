FROM debian
RUN apt-get update && apt-get install -y \
    iperf \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

EXPOSE 5001
CMD ["iperf", "-s", "-P 1"]
