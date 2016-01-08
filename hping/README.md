
### hping

[hping](http://wiki.hping.org/33) is useful for both scanning networks and crafting packets.

Example Usage:

Send TCP SYN packets to port 80:

```
$ docker run -it --rm gophernet/hping  github.com -SV -p 80
```

Send TCP SYN packets to port 80 with a 2 second interval between sends:

```
docker run -it --rm gophernet/hping  github.com -i 2 -SV -p 80
```

Send a count of 10 TCP SYN to port 80 and then exit:

```
docker run -it --rm gophernet/hping  github.com -c 10 -SV -p 80
```

Send a count of 20 TCP SYN packets to port 80 with `--fast` mode (10 packets per/second):

```
docker run -it --rm gophernet/hping  github.com --fast -SV -p 80 -c 20
```

Send a count of 30 TCP SYN packets to port 80 with and interval of 100,000 microseconds (100,000 microseconds == 10 packets per/second):

```
docker run -it --rm gophernet/hping  github.com  -i u100000 -SV -p 80 -c 30
```
