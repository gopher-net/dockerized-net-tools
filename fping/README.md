### fping

[Fping](http://fping.org/fping.1.html) for network testing e.g. ping on steroids.

*Example Fping Usage:*

* View the help options

```
$ docker run -it --rm gophernet/fping -help
```

* Ping a range of addresses (with output):

```
$ docker run -it --rm gophernet/fping -g -r 1 192.168.1.130 192.168.1.140

192.168.1.130 is alive
192.168.1.131 is alive
192.168.1.132 is alive
192.168.1.133 is alive
192.168.1.134 is alive
192.168.1.135 is unreachable
192.168.1.136 is unreachable
192.168.1.137 is unreachable
192.168.1.138 is unreachable
192.168.1.139 is unreachable
192.168.1.140 is unreachable
```

* Another method to ping a range of addresses

```
$ docker run -it --rm gophernet/fping echo 10.1.5.{1,2,3,4,5} | fmt -1 | fping
```

* Ping and print the latency of a range of hosts represented by a network CIDR notation

```
$ docker run -it --rm gophernet/fping -aeg 192.168.1.0/24
```

* Ping a range of hosts and record the output and latency to a text file named `uptime.txt`

```
$ docker run -it --rm gophernet/fping -aeg 192.168.1.0/24 > uptime.txt
```
