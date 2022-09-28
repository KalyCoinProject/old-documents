# Repositories

We've published our official Kalycoin repository on [https://github.com/KalyCoinProject](https://github.com/KalyCoinProject)  this repository supports the following distributions:

### **Debian**

·         8.x (Jessie)

·         9.x (stretch)

·         10x (Buster)

·         Testing (Bullseye)

·         Unstable (Sid)

### **Ubuntu**

16.04 - 20.10

**Mint**

18.x

****

### **Tutorial focus**

This tutorial assumes you have a basic knowledge of Linux and terminal usage, the entire process uses the Linux terminal.

### **Installing on Ubuntu**

### **Obtaining signing key**

First, we need to obtain the Kalycoin signing key from the ubuntu keyserver, here's how:

<figure><img src=".gitbook/assets/imagen (36).png" alt=""><figcaption></figcaption></figure>

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BF5B197D

This will download and add the Kalycoin signing key to your linux install.



#### Validate and Reproduce Binaries

Kalycoin uses a tool called Gitian to make reproducible builds that can be verified by anyone. Instructions on setting up a Gitian VM and building Kalycoin are provided in [Gitan Building](https://github.com/kalycoinproject/kalycoin/blob/main/doc/gitian-building.md)

#### Build on Ubuntu

This is a quick start script for compiling Kalycoin on Ubuntu

```
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev libgmp3-dev
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

# If you want to build the Qt GUI:
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler qrencode

git clone https://github.com/kalycoinproject/kalycoin --recursive
cd kalycoin

# Note autogen will prompt to install some more dependencies if needed
./autogen.sh
./configure 
make -j2
```

#### Build on CentOS

Here is a brief description for compiling Kalycoin on CentOS, for more details please refer to [the specific document](https://github.com/kalycoinproject/kalycoin/blob/main/doc/build-unix.md)

```
# Compiling boost manually
sudo yum install python-devel bzip2-devel
git clone https://github.com/boostorg/boost.git
cd boost
git checkout boost-1.66.0
git submodule update --init --recursive
./bootstrap.sh --prefix=/usr --libdir=/usr/lib64
./b2 headers
sudo ./b2 -j4 install

# Installing Dependencies for Kalycoin
sudo yum install epel-release
sudo yum install libtool libdb4-cxx-devel openssl-devel libevent-devel gmp-devel

# If you want to build the Qt GUI:
sudo yum install qt5-qttools-devel protobuf-devel qrencode-devel

# Building Kalycoin
git clone --recursive https://github.com/kalycoinproject/kalycoin.git
cd kalycoin
./autogen.sh
./configure
make -j4
```

### **Sources.**

echo "deb https://repo. Kalycoin.info/apt/ubuntu/ $(lsb\_release -cs) main" |sudo tee -a /etc/apt/sources.list.d/ Kalycoin.list



### **Installing on Debian**

First, we need to make sure **sudo** is installed:

Type sudo su and press enter, if you get a password prompt, then you can move on to obtaining the public key

### **Installing sudo**

Obtain admin privileges (su to root) and then type your admin user (root) password

Once you're logged in as "root" please type the following: apt-get install sudo

When sudo finishes installing, add your user to the sudo group: gpasswd -a youruser sudo Logout and then log in again.

### **Installing dirmngr and apt-transport-https**

These two packages are needed to enable the Kalycoin repository on Debian, let's install them:

apt install -y apt-transport-https dirmngr

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BF5B197D

This downloads and installs the Kalycoin public key

### **Adding repository to your APT sources.**

sudo su - Sudo to root first

echo "deb https://repo. Kalycoin.info/apt/debian/ buster main" >> /etc/apt/sources.list.d/ Kalycoin.list

This will add the repository to your APT sources file. **NOTE:** Please remember to change "stretch" for your Debian version codename

### **Refreshing APT sources and installing Kalycoin**

sudo apt update && sudo apt install Kalycoin

By doing this, we'll update our sources and install Kalycoin on our debian Box

****

### **Install on Archlinux**

To install on arch, the easiest way is to use "yay" [https://aur.archlinux.org/packages/yay](https://aur.archlinux.org/packages/yay)

You can install Kalycoin using the source files, but this will take a long time to compile from source. In most cases, we recommend using the binary release with: yay Kalycoin -core-bin

This will bring up a dialog where you need to confirm that you want to install the above mentioned package, press "1" to confirm.

**Launching Kalycoin**

Launching is simple, we just go to our applications menu and scrolldown/search for Kalycoin
