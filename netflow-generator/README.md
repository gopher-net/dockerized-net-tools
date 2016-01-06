### NetFlow generator

This app will generate generic [NetFlow](https://en.wikipedia.org/wiki/NetFlow) data and send it to the specified IP/Port of the NetFlow collector. It can be helpful for testing and developing netflow collectors and application development.

Example Usage:

```
docker run -it --rm networkstatic/nflow-generator -t IP_ADDR -p UDP_PORT
```

NetFlow Transport Protocol is UDP. This means the NetFlow app has no idea if there is a collector listening and receiving traffic since UDP is connectionless.  

```
$ docker run -it --rm networkstatic/nflow-generator -t 172.16.86.138 -p 9995

INFO[0000] sending netflow data to a collector ip: 172.16.86.138 and port: 9995.
Use ctrl^c to terminate the app.
```

If you want to generate more traffic from a particular protocol (approximately 3x the average) choose a protocol from the `--spike` options list of well-known protocols in the `--help` output. 

Example usage to spike a protocol:

```
$ docker run -it --rm networkstatic/nflow-generator --help

Usage:
  main [OPTIONS] [collector IP address] [collector port number]

Application Options:
  -t, --target= target ip address of the netflow collector
  -p, --port=   port number of the target netflow collector
  -s, --spike= run a second thread generating a spike for the specified protocol
    protocol options are as follows:
        ftp - generates tcp/21
        ssh  - generates tcp/22
        dns - generates udp/54
        http - generates tcp/80
        https - generates tcp/443
        ntp - generates udp/123
        snmp - generates ufp/161
        imaps - generates tcp/993
        mysql - generates tcp/3306
        https_alt - generates tcp/8080
        p2p - generates udp/6681
        bittorrent - generates udp/6682

```

Source code is located at [nerdalert/nflow-generator](https://github.com/nerdalert/nflow-generator). Feel free to contribute, fork or bugfix if it is helpful.