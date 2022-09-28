# Build Kalycoin

### **Building Kalycoin Core**

**Installing dependencies (This will work for Ubuntu and Debian)**

```
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev libgmp3-dev
```

### **Compiling Kalycoin Core from source**

### **From Github source:**

```
git clone https://github.com/ Kalycoin project/ Kalycoin --recursive
cd Kalycoin && make -C depends/
DEPENDS="$(pwd)/depends/x86_64-pc-linux-gnu"
./autogen.sh
./configure --prefix=$DEPENDS
make
make install
```

This will install all the Kalycoin binaries on depends/x86\_64-pc-linux-gnu

### **From a release file:**

```
wget https://github.com/ Kalycoin project/ Kalycoin /archive/refs/tags/mainnet-fastlane-v0.20.2.tar.gz
tar -xpf mainnet-fastlane-v0.20.2.tar.gz && cd Kalycoin -mainnet-fastlane-v0.20.2
git clone --recursive https://github.com/ Kalycoin project/cpp-eth- Kalycoin.git src/cpp-ethereum
make -C depends/
DEPENDS="$(pwd)/depends/x86_64-pc-linux-gnu"
./autogen.sh
./configure --prefix=$DEPENDS
make
make install
```

This will install all the Kalycoin binaries on depends/x86\_64-pc-linux-gnu

### **Running Kalycoin Core**

Type from a terminal:

Kalycoin d -daemon

Also, make sure to create a Kalycoin.conf with your credentials if needed for accessing RPC calls.

This is a sample Kalycoin.conf file

```
rpcuser= Kalycoin
rpcassword=coin
server=1
rpcallowip=127.0.0.1
logevents=1
daemon=1
```

### **KRC20 Tokens on Kalycoin Core**

### **Enabling Log events**

add logevents=1 to the Kalycoin.conf file before launching the daemon

Run Kalycoin like this:

kalycoind -daemon -logevents -txindex=1

If Kalycoin has already synced, you'll need to reindex blocks:

kalycoind -daemon -reindex

### **KRC20 token deep dive**

[https://docs. Kalycoin.site/en/Raw-KRC20-Transaction-implementation-guide](https://docs.qtum.site/en/Raw-QRC20-Transaction-implementation-guide)

[https://docs. Kalycoin.site/en/KRC20-integration.html](https://docs.qtum.site/en/QRC20-integration.html)
