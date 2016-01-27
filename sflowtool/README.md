### sflowtool

[sflow](http://sflow.org/) for network traffic monitoring

*Example sflow Usage:*

* Run the collector

```
$ docker run -d -p 6343:6343/udp fredhsu/sflowtool
```

* Configure your device to send sFlow data to the Docker host

* Grab the sflow output

```
$ docker logs <containerid>
```
