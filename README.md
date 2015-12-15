# dockerized-net-tools 

### A Collection of Dockerized Open Source Network Monitoring, Performance and Management Related Tools



There are some great networking tools out there. The challenge is they often have some finicky dependencies or are for a specific platform or OS. Network routers and switches are becoming more and more like servers, this will include the ability to run Docker on switches. 

In order to take advantage of the ability to start managing networks with similar tools used in other distributed systems. We are using Docker to learn new applications and share them with the networking community. Please don't hesitate to jump in and contribute. See the bottom of the page for how to contribute!

### Pre-Requisites

This is intended for folks interested in networks and there are no knowledge pre-requisites. If totally new to Docker or virtualization in general it may help to take a look at the free [Docker Training](https://training.docker.com) via Docker inc.

**Docker Engine**: This is the base Docker component. Simply install Docker engine for your target OS with these [instructions](https://docs.docker.com/engine/installation/). A quick install for Linux is `curl -sSL https://get.docker.com/ | sh` or using wget with `wget -qO- https://get.docker.com/ | sh` that executes this script [here](https://get.docker.com). 

**Docker Compose**: *(Optional)* Some of the examples may use Docker Compose for multi-container (multi-process) applications stacks. Docker Toolbox is the easiest way to install all of the Docker tools for your environment using these [instructions for Windows or Mac](https://www.docker.com/docker-toolbox). For Linux see [here](https://docs.docker.com/compose/install/).

### nmap

Nmap is a perennial favorite for security fuzzing.

*Example NMAP Usage:*

* Scan a single host for all open TCP ports with `-sS` (TCP SYN scan) 

```
$ docker run -it --rm networkstatic/nmap -sT 192.168.1.1
```

* Scan for open ssh (tcp/22) ports on a range of IPs.

```
$ docker run -it --rm networkstatic/nmap -sS 192.168.1.1-100 -p 22
```

* As with most of the apps listed, add `--help` to view additional options.

```
$ docker run -it --rm networkstatic/nmap --help
```

### fping

[Fping](http://fping.org/fping.1.html) for network testing. It's ping on steroids.

*Example Fping Usage:*

* View the help options

```
$ docker run -it --rm networkstatic/fping -help
```

* Ping a range of IP addresses

```
$ docker run -it --rm networkstatic/fping echo 10.1.5.{1,2,3,4,5} | fmt -1 | fping
```


### Contributing to the Net Tools List

Please do a pull request with your additions of tools. They don't have to be tools you created or maintain, simply add apps and show how to use it with Docker for simplicity. 

If you have any questions about how to do a [pull request](https://help.github.com/articles/using-pull-requests/) please open an [issue](https://github.com/gopher-net/dockerized-net-tools/issues) for assistance. This is here for networking professionals to learn, as such there are no bad questions and no jerks allowed :-) If you find a bug or typo you can either patch it with a pull request (PR) or open a bug in issues.
