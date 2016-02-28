
### Docker 101

This 10 minute tutorial will walk you through some basics of Docker. Since most people new to containers are comfortable with operating systems, this tutorial shows you how to run containers like an OS and then progresses to building an app. 

Any relatively modern Linux distribution has been containerized. You simply start a bash shell that has the look and feel of a full blown VM, but with a fraction of the  size. Most are less then 100MB. 


<img width="650" align="center" alt="docker_image_size" src="https://cloud.githubusercontent.com/assets/1711674/13371001/26f77104-dce9-11e5-972e-d05af0e01cb3.png"> 

### Start an Alpine Linux Container


The first example is using [Alpine Linux](http://www.alpinelinux.org) is a lightweight Linux distro based on libc and busybox. The image is 5MB and includes a package manager. Devices like your AppleTV and IoT devices run Alpine. Many webscale organizations are starting to adopt small images like Alpine enabling them to run the bare minimum and arguably reduce the attack vector.

Once inside of the OS, you can install apps from the OS's [package manager](http://dl-3.alpinelinux.org/alpine/edge/testing/x86_64/) or install a compiler and install from source. 

Figure 1. Size comparisons of the most popular Linux distributions used on Docker Hub.

*Run a Shell in Alpine*

It is as simple as a `docker run` that loads the alpine image and starts a shell with `/bin/sh`

```
$ docker run -it --rm alpine /bin/sh
```

Once inside of the shell, you can install the app you want to run. The example installs the network utility [fping](https://github.com/gopher-net/dockerized-net-tools/tree/master/fping).

```
$ apk update 
$ apk add fping
```

The first example used the `--rm` option which means when you exit the shell, the container deletes itself. If you want an image to not delete when you exit it, simply run the following.

```
# Start the container with the -d daemon option
$ docker run -itd alpine /bin/sh
d7e18df39695b10b83bb3b6de9c3240c409caa7892cc6b5650e5bdae89e74e62

# Get the Container ID (d7e18df39695)
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
d7e18df39695        alpine              "/bin/sh"           6 seconds ago       Up 6 seconds                            mad_banach

# Next start a /bin/sh process to attach to the running shell. 
# This will actually start a second shell, so that when you
# exit the first shell you started won't exit and stop the container.
# Use the Container ID from 'docker ps' with the 'docker exec' command.
$ docker exec -it d7e18df39695 sh

# Run whatever commands you want inside the container
/ # ps -ea
PID   USER     TIME   COMMAND
    1 root       0:00 /bin/sh
   25 root       0:00 sh
   34 root       0:00 ps -ea

# Ping something for funz
/ # ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: seq=0 ttl=45 time=28.989 ms

# Exit the Alpine shell dropping you back to the docker host
$ exit

# Back in the host OS, run docker ps again and you will see the container
# is still running in `-d` mode in the background. Docker exec to reattach.
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
d7e18df39695        alpine              "/bin/sh"           5 minutes ago       Up 5 minutes                            mad_banach

```

### Build Your Own Image

You will also use the distributions to build your Dockerfiles. Here is the Dockerfile from the fping repository. By default Docker looks for a a file named `Dockerfile` in the current directory when you build a local image. 

1. Create a text file with the following in it named `Dockerfile`

```
# fping in a container
# 
# Dockerfile will execute fping and any arguments passed.
# Example: docker run -it --rm gophernet/fping -help
#
FROM alpine:latest

MAINTAINER Brent Salisbury <brent.salisbury@gmail.com>

# build initial cache | install binary | remove cache
RUN apk update && apk add \
	fping \
	&& rm -rf /var/cache/apk/*

ENTRYPOINT ["fping"]
```

2. From in the same directory as the Dockerfile, build it. The name of the Docker image that will be created is `gopherz-img`.

```
docker run -it gopherz-img -h
```

3. List all docker images on the host. You will see the new image you just built, along with the Alpine image you pulled down in the first example.

```
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
gopherz-img         latest              09c60c61f810        4 minutes ago       4.873 MB
alpine              latest              90239124c352        9 days ago          4.794 MB
```

4. Now you can run the app image you just built. It is the equivalent of running `fping --help` on an operating system with fping installed, but in the case it is simply 5MB done in a fraction of a second.

```
docker run -it gopherz-img --help
```

### Other Popular Distributions

Other popular distributions can be run just as easily.

```
docker run -it --rm ubuntu
docker run -it --rm debian
docker run -it --rm fedora
docker run -it --rm centos
docker run -it --rm busybox
```

### More Tutorials

If you have tutorials from the community please feel free to add them:

- Good video series by [@botchagalupe](https://twitter.com/botchagalupe) check out the videos on the [Docker Youtube channel](https://www.youtube.com/watch?v=uTe08FxoKrU&list=PLkA60AVN3hh_6cAz8TUGtkYbJSL2bdZ4h&index=2)
- List of Docker tutorials [hackr.io](http://hackr.io/tutorials/docker).
- Long [tutorial](http://prakhar.me/docker-curriculum/) with some good app examples.)
- [Webinar and tutorials](https://github.com/Mierdin/intro-to-docker-workshop) from [@mierdan](https://twitter.com/Mierdin) and [@ioshints](https://twitter.com/ioshints).

Happy hacking!

