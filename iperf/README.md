### iperf

[iperf](https://iperf.fr/) is a tool for measuring bandwidth performance.  It runs as a client to send the traffic and a server to receive the traffic.

*Example iperf Usage:*

* Run the server on one node.  You will need to expose a port and make note of the IP address of the host.

```
$ docker pull fredhsu/iperf-server
$ docker run -p 5001:5001 fredhsu/iperf-server 
```

* Run the client on another node

```
$ docker pull fredhsu/iperf-client
$ docker run fredhsu/iperf-client <ip addr of the server node>
```
