### nmap

[Nmap](https://nmap.org) is a perennial favorite for security fuzzing.

*Example NMAP Usage:*

* Scan a single host for all open TCP ports with `-sS` (TCP SYN scan) 

```
$ docker run -it --rm networkstatic/nmap -sT 192.168.1.1
```

* Scan for open ssh (tcp/22) ports on a range of IPs.

```
$ docker run -it --rm networkstatic/nmap -sS 192.168.1.1-100 -p 22
```

* Scan multiple hosts

```
nmap 192.168.1.1 192.168.1.2 192.168.1.3
```

* Scan a range of hosts (192.168.1.1 through 192.168.1.50)

```
nmap 192.168.1.1-50
```
* Scan a range of hosts for a specified range of ports (70 through 90)

```
nmap 192.168.1.1-50 -p 70-90
```

* As with most of the apps listed, add `--help` to view additional options.

```
$ docker run -it --rm networkstatic/nmap --help
```

More detailed usage at [nmap.org](https://nmap.org/book/man-briefoptions.html)