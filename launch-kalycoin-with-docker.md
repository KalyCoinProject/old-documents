# Launch Kalycoin with docker

### **How to run Kalycoin node with docker**

### **Quick start**

This tutorial use Linux Ubuntu as example, OSX and windows platform are almost the same.

Suppose the reader has basic command line knowledge, and also have docker correctly installed and configured. If not, please learn about command line and Docker first.

For more details, please refer to [github](https://github.com/KalyCoinProject/KalyCoin)

### **Get docker image**

You might take either way:

### **Pull a image from Public Docker hub**

$ docker pull Kalycoin / Kalycoin

### **Or, build Kalycoin image with provided Dockerfile**

The Dockerfile can be downloaded on github: [Dockerfile](https://github.com/KalyCoinProject/documents/blob/main/en/Launch-KalyCoin-with-Docker.md)

$docker build --rm -t Kalycoin / Kalycoin .

For historical versions, please visit [docker hub](https://hub.docker.com/r/kalycoin/kalycoin)

### **Prepare data path and Kalycoin.conf**

In order to use user-defined config file, as well as save block chain data, -v option for docker is recommended.

First chose a path to save Kalycoin block chain data:

sudo rm -rf /data/ Kalycoin -data

sudo mkdir -p /data/ Kalycoin -data

sudo chmod a+w /data/ Kalycoin -data

Create your config file, refer to the example \[Kalycoin.conf]!([https://github.com/ Kalycoin project/ Kalycoin /blob/1a926b980f03e97322c7dd787835bec1730f35d2/contrib/debian/examples/ Kalycoin.conf](https://github.com/kalycoinproject/kalycoin/blob/1a926b980f03e97322c7dd787835bec1730f35d2/contrib/debian/examples/qtum.conf)). Note rpcuser and rpcpassword to required for later Kalycoin -cli usage for docker, so it is better to set those two options. Then please create the file ${PWD}/ Kalycoin.conf with content:

rpcuser= Kalycoin

rpcpassword= Kalycoin test

### **Launch Kalycoin d**

To launch Kalycoin node:

\## to launch Kalycoin d

$ docker run -d --rm --name Kalycoin \_node \\

&#x20;            \-v ${PWD}/ Kalycoin.conf:/root/. Kalycoin / Kalycoin.conf \\

&#x20;            \-v /data/ Kalycoin -data/:/root/. Kalycoin / \\

&#x20;            Kalycoin / Kalycoin Kalycoin d

&#x20;

\## check docker processed

$ docker ps

&#x20;

\## to stop Kalycoin d

$ docker run -i --network container: Kalycoin \_node \\

&#x20;            \-v ${PWD}/ Kalycoin.conf:/root/. Kalycoin / Kalycoin.conf \\

&#x20;            \-v /data/ Kalycoin -data/:/root/. Kalycoin / \\

&#x20;            Kalycoin / Kalycoin Kalycoin -cli stop

${PWD}/ Kalycoin.conf will be used, and blockchain data saved under /data/ Kalycoin -data/

### **Interact with Kalycoin d using Kalycoin -cli**

Use following docker command to interact with your Kalycoin node with Kalycoin -cli:

$ docker run -i --network container: Kalycoin \_node \\

&#x20;            \-v ${PWD}/ Kalycoin.conf:/root/. Kalycoin / Kalycoin.conf \\

&#x20;            \-v /data/ Kalycoin -data/:/root/. Kalycoin / \\

&#x20;            Kalycoin / Kalycoin Kalycoin -cli getinfo

For more Kalycoin -cli commands, use:

$ docker run -i --network container: Kalycoin \_node \\

&#x20;            \-v ${PWD}/ Kalycoin.conf:/root/. Kalycoin / Kalycoin.conf \\

&#x20;            \-v /data/ Kalycoin -data/:/root/. Kalycoin / \\

&#x20;            Kalycoin / Kalycoin Kalycoin -cli help

&#x20;
