
### traceroute

[traceroute](http://manpages.ubuntu.com/manpages/jaunty/man8/traceroute-nanog.genuine.8.html) print the route that IP packets traverse going to a remote host.

Have you ever been on a system or a network switch and noticed there is some proprietary `ping` or `traceroute` without any of the options you need? Well, we have :p so lets get basic with traceroute> 

*Note*: You may notice there is not a Dockerfile in this directory. This is because small OS images like [Alpine Linux](https://hub.docker.com/_/alpine/) and [Busybox](https://hub.docker.com/_/busybox/) come with Traceroute and other basic troubleshooting apps installed. So we will simply pass the desired app after the OS name like so `docker run -it --rm DISTRO APP`. 

```
$ docker run -it --rm alpine traceroute 

Usage: traceroute [-46FIlnrv] [-f 1ST_TTL] [-m MAXTTL] [-q PROBES] [-p PORT]
	[-t TOS] [-w WAIT_SEC] [-g GATEWAY] [-s SRC_IP] [-i IFACE]
	[-z PAUSE_MSEC] HOST [BYTES]

Trace the route to HOST

	-4,-6	Force IP or IPv6 name resolution
	-F	Set don't fragment bit
	-I	Use ICMP ECHO instead of UDP datagrams
	-l	Display TTL value of the returned packet
	-n	Print numeric addresses
	-r	Bypass routing tables, send directly to HOST
	-v	Verbose
	-f N	First number of hops (default 1)
	-m N	Max number of hops
	-q N	Number of probes per hop (default 3)
	-p N	Base UDP port number used in probes
		(default 33434)
	-s IP	Source address
	-i IFACE Source interface
	-t N	Type-of-service in probe packets (default 0)
	-w SEC	Time to wait for a response (default 3)
	-g IP	Loose source route gateway (8 max)
```

Example Usage with a target site (github.com):

```
docker run -it --rm alpine traceroute github.com

traceroute to github.com (192.30.252.131), 30 hops max, 46 byte packets
 1  172.17.0.1 (172.17.0.1)  0.005 ms  0.004 ms  0.001 ms
 2  10.0.2.2 (10.0.2.2)  0.074 ms  0.117 ms  0.215 ms
 .....
```

To exit the trace prior to the trace finishing, use `Control+P+Q` twice to detach and `Control+C` to exit the container.

### traceroute6

[traceroute6](http://manpages.ubuntu.com/manpages/oneiric/man8/traceroute6.iputils.8.html) is also available by default on almost any OS image.
```
docker run -it --rm alpine traceroute6

BusyBox v1.24.1 (2015-12-08 16:43:56 UTC) multi-call binary.

Usage: traceroute6 [-nrv] [-m MAXTTL] [-q PROBES] [-p PORT]
	[-t TOS] [-w WAIT_SEC] [-s SRC_IP] [-i IFACE]
	HOST [BYTES]

Trace the route to HOST

	-n	Print numeric addresses
	-r	Bypass routing tables, send directly to HOST
	-v	Verbose
	-m N	Max number of hops
	-q N	Number of probes per hop (default 3)
	-p N	Base UDP port number used in probes
		(default 33434)
	-s IP	Source address
	-i IFACE Source interface
	-t N	Type-of-service in probe packets (default 0)
	-w SEC	Time wait for a response (default 3)
```
