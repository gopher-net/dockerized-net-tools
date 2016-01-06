
### netcat

[Netcat](http://netcat.sourceforge.net) is a featured networking utility which reads and writes data across network connections, using the TCP/IP protocol.

Start a listener and map a port to be connected to from another container or host (-p 9000:9000 will port forward e.g. NAT the container to the host OS IP address):

```
$ docker run -it --rm  -p 9000:9000 networkstatic/netcat -l 9000
```

Get the IP of the docker instance:

```
$ docker inspect --format "{{ .NetworkSettings.IPAddress }}" $(docker ps -q)
```

Connect to the listener w/ a new container:

```
 $ docker run -it --rm  networkstatic/netcat 172.17.0.1 9000
```

Breaking out of the shell can be squirrely since netcat will tie it up. Control+P+Q twice to detach and Control+C to exit the container.