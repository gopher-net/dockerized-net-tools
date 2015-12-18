FROM debian
RUN apt-get update && apt-get install -y \
    iperf \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["iperf", "-c"]
CMD ["localhost"]
