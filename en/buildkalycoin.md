# Building Kalycoin Core

### Installing dependencies (This will work for Ubuntu and Debian)

```bash
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev libgmp3-dev
```

## Compiling Kalycoin Core from source

### From Github source:



```bash
git clone https://github.com/kalycoinproject/kalycoin --recursive
cd kalycoin && make -C depends/
DEPENDS="$(pwd)/depends/x86_64-pc-linux-gnu"
./autogen.sh
./configure --prefix=$DEPENDS
make
make install
```

This will install all the Kalycoin binaries on `depends/x86_64-pc-linux-gnu`

### From a release file:

```bash
wget https://github.com/kalycoinproject/kalycoin/archive/refs/tags/mainnet-fastlane-v0.20.2.tar.gz
tar -xpf mainnet-fastlane-v0.20.2.tar.gz && cd kalycoin-mainnet-fastlane-v0.20.2 
git clone --recursive https://github.com/kalycoinproject/cpp-eth-kalycoin.git src/cpp-ethereum
make -C depends/
DEPENDS="$(pwd)/depends/x86_64-pc-linux-gnu"
./autogen.sh
./configure --prefix=$DEPENDS
make
make install
```

This will install all the Kalycoin binaries on `depends/x86_64-pc-linux-gnu`

## Running Kalycoin Core

Type from a terminal: 

`kalycoind -daemon`

Also, make sure to create a kalycoin.conf with your credentials if needed for accessing RPC calls.

This is a sample kalycoin.conf file

```bash
rpcuser=kalycoin
rpcassword=coin
server=1
rpcallowip=127.0.0.1
logevents=1
daemon=1
```


# KRC20 Tokens on Kalycoin Core

## Enabling Log events

add `logevents=1` to the kalycoin.conf file before launching the daemon

Run Kalycoin like this:

`kalycoind -daemon -logevents -txindex=1`

If Kalycoin has already synced, you'll need to reindex blocks:

`kalycoind -daemon -reindex` 

## KRC20 token deep dive

https://docs.kalycoin.io/en/Raw-KRC20-Transaction-implementation-guide

https://docs.kalycoin.io/en/KRC20-integration.html

