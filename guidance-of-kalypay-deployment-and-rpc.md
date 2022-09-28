# Guidance of kalypay deployment and RPC

### **How to deploy a Kalycoin node**

This guidance includes how to deploy, run and make RPC calls.

Suppose the readers are able to use Linux,Mac or Windows command line. If you are not familiar with command line, or just interested in using GUI wallet, please refer to another document about [ Kalycoin Wallet Tutorial](https://docs.kalycoin.io/desktop-wallet-basic-usage).

### **Get Kalycoin Node**

There are at least 4 ways to get a Kalycoin node, you can choose any way：

### **1. Download the binaries**

If you do not care much about Kalycoin 's source code, the easiest way to abtain Kalycoin node is to download the latest binaries on the [ Kalycoin release page](https://github.com/KalyCoinProject/KalyCoin/releases). Currently it supports Linux, Window, OSX. It is highly recommanded to download the latest version. In this guidance, we will use v0.14.13 version as an example。

（Note: the version number you see might be different, here is v0.14.13, but other key words except for version are the same.）

·         For **Mac** user：Kalycoin -0.14.13-osx64.tar.gz

·         For **Linux** users： Kalycoin -0.14.13-i686-pc-linux-gnu.tar.gz(32bit) or Kalycoin -0.14.13-x86\_64-linux-gnu.tar.gz(64bit)

·         For **Windows** users：Kalycoin -0.14.13-win32.zip(32bit) or Kalycoin -0.14.13-win64.zip（64bit）

·         For **Raspberry Pi**：Kalycoin -0.14.13-arm-linux-gnueabihf.tar.gz

Decompress after downloading, then you will get Kalycoin d and Kalycoin -cli under the path \<your path>/bin.

### **2. apt install for Linux users**

Please refer to [https://github.com/KalyCoinProject/KalyCoin#building-kalycoin-core](https://github.com/KalyCoinProject/KalyCoin#building-kalycoin-core)，Current support Ubuntu，Debian and Mint。



After installation, you should be able to run kalycoind and kalycoin-cli directly in the terminal。

### **3. Compiler from source code**

If you want to compile latest Kalycoin from source code, please pull the latest source from github : [https://github.com/ Kalycoin project/ Kalycoin ](https://github.com/KalyCoinProject/KalyCoin)。

The instruction for compilation : [https://github.com/KalyCoinProject/KalyCoin#building-kalycoin-core](https://github.com/KalyCoinProject/KalyCoin#building-kalycoin-core)。Currently we recommand to compile on Linux or OSX, while other platforms might need more configuration.

After compilation, you also get Kalycoin d and Kalycoin -cli under the path \<your path>/src/

### **4. Get Kalycoin node docker image**

Suppose user has docker environment installed correctly. ([what is docker?](https://docs.docker.com/get-started/overview/))

The Kalycoin official docker image on docker hub is Kalycoin / Kalycoin, you can pull it by docker command ：

docker pull Kalycoin / Kalycoin:latest

All the four ways above cand get Kalycoin nodes. There are two important binaries which are related to deployment and RPC calls:

·         Kalycoin d：Kalycoin core program, i.e. Kalycoin fullnode program.

·         Kalycoin -cli：Kalycoin command line interface，interact with Kalycoin d, achieve RPC calls.

### **Deploy Kalycoin node**

For the instruction for Kalycoin docker images, please refer to "[How to launch Kalycoin with docker](https://github.com/KalyCoinProject/old-documents/blob/main/en/Launch-KalyCoin-with-Docker.md)".

Other normal deployment methods are almost the same, here we take Ubuntu as an example. The commands in Mac and windows are exactly the same.

Run Kalycoin fullnode with ./ Kalycoin d：

./ Kalycoin d -daemon

This with launch a Kalycoin d daemon with the option -daemon. If user are interested in the event logs about smart contract, please add one more option -logevents.

More options can be found：

./ Kalycoin d -help

To stop running：

./ Kalycoin -cli stop

The default data path for different platforms:

·         Linux：\~/. Kalycoin /

·         Mac OSX：\~/Library/Application Support/ Kalycoin

·         Windows:%APPDATA%\ Kalycoin

You can also use -datadir to set your own data path。

Kalycoin node will sync all the historical block data for first launch, and saves to datadir. It might take some time. Then diagnostics for the node can be found under the data path \~/. Kalycoin /debug.log。

### **Local RPC call**

When the Kalycoin node is running, we can use Kalycoin command line interface Kalycoin -cli to interact with Kalycoin d, and make local RPC calls.

e.g.：

```
oldclock@raven:~/ Kalycoin -0.14.3/bin$ ./ Kalycoin -cli getinfo
{
  "version": 140300,
  "protocolversion": 70016,
  "walletversion": 130000,
  "balance": 0.00000000,
  "stake": 0.00000000,
  "blocks": 12126,
  "timeoffset": 0,
  "connections": 8,
  "proxy": "",
  "difficulty": {
    "proof-of-work": 1.52587890625e-05,
    "proof-of-stake": 886731.5868738915
  },
  "testnet": false,
  "moneysupply": 100028504,
  "keypoololdest": 1505186997,
  "keypoolsize": 100,
  "paytxfee": 0.00000000,
  "relayfee": 0.00400000,
  "errors": ""
}
```

To get all RPC command list:

./kalycoin -cli help

To get help for specific RPC command, use ./ Kalycoin -cli help \<RPCcmd>，e.g.：

./kalycoin -cli help getinfo

### **JsonRPC settings**

You can get the jsonrpc example by using (here we use getinfo as an example): ./ Kalycoin -cli help getinfo

Examples:

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

The example shows detailed format for jsonrpc content. However, it can only be called after setting rpcuser and rpcpassword. There are two ways to set the parameters, you can choose either.

Method 1：Create config file \~/. Kalycoin / Kalycoin.conf，which should include:

rpcuser=test  #rpc user name, (necessary)

rpcpassword=test1234  #rpc password, (necessary)

\# By default, only local jsonrpc is allowed

\# Remote connection is allowed only when setting rpcallowip as following:

\# both ipv4 and ipv6 can be set, e.g.:

\#rpcallowip=192.168.77.51/255.255.255.0

\#rpcallowip=1.2.3.4/24

\#rpcallowip=2001:db8:85a3:0:0:8a2e:370:7334/96



After creating the config file, please restart the node to finish settings.

Method 2：Restart Kalycoin node with following options:

./ Kalycoin d -daemon -rpcuser=test -rpcpassword=test1234 -rpcallowip=192.168.77.51/255.255.255.0

The meaning of options rpcuser, rpcpassword and rpcallowip are all the same with the config file above.

### **RPC call example**

You can make remote RPC calls after the settings above. Here is an example: Suppose the Kalycoin node is running on an Ubuntu machine, whose ip is 192.168.77.188, default port=3889. Now we try to make jsonrpc call in a remote macbook:

```
zhongwenbins-MacBook-Pro:~ zhongwenbin$ curl --user test:test1234 --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getinfo", "params": [] }' -H 'content-type: text/plain;' http://192.168.77.188:3889/
{"result":{"version":140300,"protocolversion":70016,"walletversion":130000,"balance":0.00000000,"stake":0.00000000,"blocks":12197,"timeoffset":0,"connections":8,"proxy":"","difficulty":{"proof-of-work":1.52587890625e-05,"proof-of-stake":650787.7561123729},"testnet":false,"moneysupply":100028788,"keypoololdest":1505186997,"keypoolsize":100,"paytxfee":0.00000000,"relayfee":0.00400000,"errors":""},"error":null,"id":"curltest"}
```

The result is identical with local call.

You can also use tools like postman to get the same result：

### **Nginx settings（optional）**

As the example above, you might find that it is quite complicated to make remote jsonrpc, since you must include rpcuser, rpcpassword, as well as port in the command. If you don't want users to provide these parameters, we recommand using Nginx. The benefits for Nginx is not only about simplification, but also a good way to hide rpcuser, rpcpassword and port number. And you can filter some RPCs for security. Here we suppose the reader have installed Nginx and have basic knowledges about how to use it.

example:

·         Kalycoin node is running on 192.168.77.188,

·         api proxy ip 192.168.77.51, with Nginx installed

Instructions：

1.Set the Kalycoin.conf of Kalycoin node, remember to add the proxy ip to rpcallowip e.g.：

```
rpcuser=test
rpcpassword=test1234
rpcallowip=192.168.77.51/255.255.255.0
```

2.Setup Nginx ：

```
server {
        listen       80;
        server_name  localhost;
 
        location / {
            proxy_pass http://192.168.77.188:3889;  #to port 3889
            proxy_set_header Authorization "Basic dGVzdDp0ZXN0MTIzNA==";  # its the base64 encode of test:test1234
        }
    }
```

&#x20;  &#x20;

3.Then you can make remote rpc call through proxy, without rpcuser or rpcpassword. e.g.：

```
zhongwenbins-MacBook-Pro:~ zhongwenbin$ curl  --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getinfo", "params": [] }' -H 'content-type: text/plain;' http://192.168.77.51/
{"result":{"version":140300,"protocolversion":70016,"walletversion":130000,"balance":0.00000000,"stake":0.00000000,"blocks":12250,"timeoffset":0,"connections":8,"proxy":"","difficulty":{"proof-of-work":1.52587890625e-05,"proof-of-stake":651324.7815933984},"testnet":false,"moneysupply":100029000,"keypoololdest":1505186997,"keypoolsize":100,"paytxfee":0.00000000,"relayfee":0.00400000,"errors":""},"error":null,"id":"curltest"}
```

This is only a simple example. You might have different settings or tools instead.

### **Useful commands and documents**

If you have any questions during node deployment and RPC calls, here are some useful documents to refer to:

·         For source code compilation issues： [https://github.com/KalyCoinProject/KalyCoin#readme](https://github.com/KalyCoinProject/KalyCoin#readme)

·         Command to check all Kalycoin d options：./ Kalycoin d -help

·         Command to get all RPC list： ./kalycoin -cli help

·         Get RPC help（like getinfo）： ./kalycoin -cli help getinfo



###
