### iperf

[iperf](https://iperf.fr/) is a tool for measuring bandwidth performance.  It runs as a client to send the traffic and a server to receive the traffic.

*Example iperf Usage:*

* Run the server on one node.  You will need to expose a port and make note of the IP address of the host.

```
$ docker pull gophernet/iperf-server
$ docker run -p 5001:5001 gophernet/iperf-server 
```

* Run the client on another node

```
$ docker pull gophernet/iperf-client
$ docker run gophernet/iperf-client <ip addr of the server node>
```
