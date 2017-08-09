FROM alpine:3.5

RUN apk add --update git go make gcc musl-dev linux-headers bash pwgen
RUN git clone https://github.com/ethereum/go-ethereum.git

RUN \
  (cd go-ethereum && make geth && make swarm)             && \
  cp go-ethereum/build/bin/geth /usr/local/bin/           && \
  cp go-ethereum/build/bin/swarm /usr/local/bin/           && \
  apk del git go make gcc musl-dev linux-headers          && \
  rm -rf /go-ethereum && rm -rf /var/cache/apk/*

ADD start-swarm /root/start-swarm
RUN chmod +x /root/start-swarm

ENTRYPOINT /root/start-swarm

