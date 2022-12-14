# Janus Docker Container

First, download the Janus docker image

```
docker pull ripply/janus:latest
```

To setup a Janus docker container we need to configure a network bridge for it to talk to the Kalycoin blockchain

```
docker network create --driver bridge kalycoin
```

Then we need to startup the Kalycoin blockchain and configure it to use the network

```
docker run --network=kalycoin -it --rm \
  --name kalycoind_regtest \
  -v `pwd`:/root \
  -p 23888:23888 \
  -p 3889:3889 \
  kalycoin/kalycoin \
  kalycoind -regtest -txindex -addrindex=1 -logevents \
  -rpcbind=0.0.0.0:3889 -rpcallowip=0.0.0.0/0 -rpcuser=kalycoin -rpcpassword=testpasswd
```

And finally, launch Janus configured to use the network as well

```
docker run --network=kalycoin -it --rm \
  --name janus_regtest \
  -v `pwd`:/root \
  -p 23889:23889 \
  ripply/janus:latest \
  --bind 0.0.0.0 --dev --kalycoin-rpc=http://kalycoin:testpasswd@kalycoind_regtest:3889
```


