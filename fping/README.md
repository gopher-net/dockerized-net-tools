### fping

[Fping](http://fping.org/fping.1.html) for network testing e.g. ping on steroids.

*Example Fping Usage:*

* View the help options

```
$ docker run -it --rm networkstatic/fping -help
```

* Ping a range of IP addresses

```
$ docker run -it --rm networkstatic/fping echo 10.1.5.{1,2,3,4,5} | fmt -1 | fping
```

* Ping and print the latency of a range of hosts represented by a network CIDR notation

```
$ docker run -it --rm networkstatic/fping -aeg 192.168.1.0/24
```

* Ping a range of hosts and record the output and latency to a text file named `uptime.txt`

```
$ docker run -it --rm networkstatic/fping -aeg 192.168.1.0/24 > uptime.txt
```