
### traceroute6

[traceroute6](http://manpages.ubuntu.com/manpages/oneiric/man8/traceroute6.iputils.8.html) - traces path to an IPv6 network node.

```
$ docker run -it --rm gophernet/traceroute6

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

To exit the trace prior to the trace finishing, use `Control+P+Q` twice to detach and `Control+C` to exit the container.
