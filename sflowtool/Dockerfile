FROM alpine:3.3
RUN apk add --update git build-base
ADD https://github.com/sflow/sflowtool/releases/download/v3.37/sflowtool-3.37.tar.gz sflowtool-3.37.tar.gz
RUN tar -zxvf sflowtool-3.37.tar.gz
WORKDIR sflowtool-3.37
RUN ./configure
RUN make
RUN make install
EXPOSE 6343/udp
CMD ["sflowtool"]
