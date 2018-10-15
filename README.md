# dockerized-net-tools 

### A Collection of Dockerized Open Source Network Monitoring, Performance and Management Related Tools

There are some great networking tools out there. The challenge is they often have some finicky dependencies or are for a specific platform or OS. Network routers and switches are becoming more and more like servers, this will include the ability to run Docker on switches. 

In order to take advantage of the ability to start managing networks with similar tools used in other distributed systems. We are using Docker to learn new applications and share them with the networking community. Please don't hesitate to jump in and contribute. See the bottom of the page for how to contribute!

### Pre-Requisites

- This is intended for folks interested in networks and there are no knowledge pre-requisites. If totally new to Docker or virtualization in general it may help to take a look at the free [Docker Training](https://training.docker.com) via Docker inc.

- There is a 10 minute tutorial in this repository that will give you a simple overview of running containers and building your own image in the [docker-tutorial](https://github.com/gopher-net/dockerized-net-tools/tree/master/docker-tutorial) directory.

**Docker Engine**: This is the base Docker component. Simply install Docker engine for your target OS with these [instructions](https://docs.docker.com/engine/installation/). A quick install for Linux is `curl -sSL https://get.docker.com/ | sh` or using wget with `wget -qO- https://get.docker.com/ | sh` that executes this script [here](https://get.docker.com). 

**Docker Toolbox (Easiest for Mac/Win)**: will install all of the relevant [Docker Tools](https://www.docker.com/docker-toolbox).

### Tools and Examples for Getting Started

Below are links to each tools directory in this repository with an example Dockerfile and usage.

* [drill](https://github.com/gopher-net/dockerized-net-tools/tree/master/drill) is a tool from `ldns` that is a replacement for `dig`.

* [fping](https://github.com/gopher-net/dockerized-net-tools/tree/master/fping) - tool for measuring latency, status and all around ping on steroids. 

* [hping](https://github.com/gopher-net/dockerized-net-tools/tree/master/hping) is useful for both scanning networks and crafting packets.

* [iperf](https://github.com/gopher-net/dockerized-net-tools/tree/master/iperf) - extremely versatile tool for measuring network bandwidth and performance. 

* [mz](https://github.com/gopher-net/dockerized-net-tools/tree/master/mz) Mausezahn is a fast traffic generator which allows you to send nearly any kind of packet.

* [nmap](https://github.com/gopher-net/dockerized-net-tools/tree/master/nmap) - security scanner, port scanner and network discovery tool

* [netcat](https://github.com/gopher-net/dockerized-net-tools/tree/master/netcat) - security scanner, port scanner and network discovery tool

* [netflow generator](https://github.com/gopher-net/dockerized-net-tools/tree/master/netflow-generator) - generate generic NetFlow data and send it to the specified IP/Port of the NetFlow collector.

* [sflowtool](https://github.com/gopher-net/dockerized-net-tools/tree/master/sflowtool) - sFlow collector

* [traceroute](https://github.com/gopher-net/dockerized-net-tools/tree/master/traceroute) print the route that IP packets traverse going to a remote host.

* [traceroute6](https://github.com/gopher-net/dockerized-net-tools/tree/master/traceroute6) print the route IPv6 packets will take to a network node.

### Network Hardware Vendor Docker Support

We will track and link to the network vendors supporting Docker and this method of tooling for network ops/dev.

* [Arista Networks](http://www.arista.com)

### Contributing to the Net Tools List

Please do a pull request with your additions of tools. They don't have to be tools you created or maintain, simply add apps and show how to use it with Docker for simplicity. 

If you have any questions about how to do a [pull request](https://help.github.com/articles/using-pull-requests/) please open an [issue](https://github.com/gopher-net/dockerized-net-tools/issues) for assistance. This is here for networking professionals and network devs to explore, learn and innovate. As such there are no bad questions and no jerks allowed :-) If you find a bug or typo you can either patch it with a pull request (PR) or open a bug in issues.
